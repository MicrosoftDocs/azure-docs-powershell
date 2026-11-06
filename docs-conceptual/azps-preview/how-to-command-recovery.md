---
title: Discover commands and troubleshoot Azure PowerShell preview
description: Find preview cmdlets, inspect their parameters, use authenticated Azure Resource Manager REST requests, and collect diagnostic information.
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: how-to
ms.date: 10/28/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-generated
---

# Discover commands and troubleshoot Azure PowerShell preview

In this article, you find the right Azure PowerShell preview cmdlet for a task, fall back to an authenticated REST request when there's no cmdlet for it, and collect the information you need to recover from a failed command.

By the end of this article, you've inspected a cmdlet's syntax and examples, created and verified a resource that has no dedicated preview cmdlet by using `Invoke-AzRestMethod`, inspected a controlled failure, and removed everything that the article created.

## Prerequisites

- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- An Azure subscription and permission to create a test resource group and a storage account.

## Discover commands

List the resource-group commands in the loaded preview module and inspect the parameters of the creation cmdlet.

```powershell
Get-Command -Module Az.Resources -Name '*ResourceGroup*'
Get-Command New-AzResourceGroup -Syntax
Get-Help New-AzResourceGroup -Examples
Get-Module Az.Resources | Select-Object Name, Version, Path
```

The first command lists the matching cmdlets, such as `Get-AzResourceGroup`, `New-AzResourceGroup`, `Set-AzResourceGroup`, `Remove-AzResourceGroup`, and the resource-group deployment cmdlets. The second command shows the syntax of `New-AzResourceGroup`, including its required `-Name` and `-Location` parameters. The last command shows a module version in the `0.1.x` series and a path in your preview installation, not a classic installation. If local help doesn't include examples, use the [preview cmdlet reference](/powershell/module/?view=azps-preview&preserve-view=true).

## Create a test resource group

Replace the subscription and location placeholders before running these commands. Use the same session for the remaining examples.

```powershell
$ErrorActionPreference = 'Stop'
$sub = '<test-subscription-id>'
$location = '<region>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$rg = "azclips-recovery-$run"
$storage = "clips$([guid]::NewGuid().ToString('N').Substring(0, 18))"

New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
Get-AzResourceGroup -SubscriptionId $sub -Name $rg
```

Both commands return the resource group with the name and location you specified and a provisioning state of `Succeeded`.

## Send an authenticated request when there's no cmdlet

The preview doesn't include a cmdlet that creates storage accounts. Use `Invoke-AzRestMethod` to send the Azure Resource Manager request directly. The request uses the preview session's existing authentication.

Create a storage account with a `PUT` request:

```powershell
$uri = "/subscriptions/$sub/resourceGroups/$rg/providers/Microsoft.Storage/storageAccounts/${storage}?api-version=2023-05-01"
$body = @{
    location = $location
    sku      = @{ name = 'Standard_LRS' }
    kind     = 'StorageV2'
} | ConvertTo-Json
Invoke-AzRestMethod -Method PUT -Uri $uri -Payload $body -Headers @{ 'Content-Type' = 'application/json' }
```

The response shows an HTTP status code of `200` (OK) or `202` (Accepted). A `202` status means that Azure accepted the request and is still creating the storage account. `Invoke-AzRestMethod` doesn't wait for long-running operations to finish, so verify the result with a `GET` request on the same URI:

```powershell
Invoke-AzRestMethod -Method GET -Uri $uri
```

The response shows status code `200`, and the JSON body includes the storage account's name, location, `sku` set to `Standard_LRS`, `kind` set to `StorageV2`, and `properties.provisioningState`. If the provisioning state isn't `Succeeded` yet, wait a few seconds and run the `GET` request again.

The preview REST cmdlet targets Azure Resource Manager only. It doesn't automatically follow pagination or poll long-running operations. For more information, see [Invoke-AzRestMethod](/powershell/module/az.resources/invoke-azrestmethod?view=azps-preview&preserve-view=true).

## Inspect a failure

Request a resource group that doesn't exist and inspect the resulting error.

```powershell
try {
    Get-AzResourceGroup -SubscriptionId $sub -Name "$rg-missing" -ErrorAction Stop
    throw 'Missing-resource lookup unexpectedly succeeded.'
}
catch {
    if ($_.Exception.Message -like '*unexpectedly succeeded*') { throw }
    $_.Exception.Message
}
```

The output is an error message that says the resource group can't be found. Use the command name, parameters, and error message to check the preview reference and reproduce the problem. Before sharing diagnostics, redact credentials, access tokens, and sensitive output. Include the PowerShell version and preview module versions.

AI troubleshooting is available in the Azure CLI preview, not the Azure PowerShell preview. Don't run CLI recovery commands as PowerShell cmdlets. For more information, see [Recover from command failures with AI troubleshooting in Azure CLI](/cli/azure/how-to-command-recovery?view=azure-cli-preview&preserve-view=true).

## Clean up resources

Delete only the test resource group created in this article. Deletion also removes the storage account and any other resources that you added to that group.

```powershell
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Get-AzResourceGroup -SubscriptionId $sub -Name $rg -ErrorAction SilentlyContinue
```

`Remove-AzResourceGroup` returns `True` when the deletion completes. The final lookup returns no output, which confirms that the group is gone.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Troubleshoot Azure PowerShell issues](troubleshooting.md).
