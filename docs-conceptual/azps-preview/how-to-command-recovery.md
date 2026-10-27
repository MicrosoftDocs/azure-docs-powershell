---
title: Discover commands and troubleshoot Azure PowerShell preview
description: Find preview cmdlets, inspect their parameters, use authenticated Azure Resource Manager REST requests, and collect diagnostic information.
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: how-to
ms.date: 10/27/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-generated
---

# Discover commands and troubleshoot Azure PowerShell preview

Use command discovery and help to find preview cmdlets. When a dedicated cmdlet isn't available, use `Invoke-AzRestMethod` to send an authenticated request to Azure Resource Manager.

> [!IMPORTANT]
> These draft examples require end-to-end validation against the release build before use.

## Prerequisites

- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- An Azure subscription and permission to create a test resource group.

## Discover commands

List the resource-group commands in the loaded preview module and inspect the parameters of the creation cmdlet.

```powershell
Get-Command -Module Az.Resources -Name '*ResourceGroup*'
Get-Command New-AzResourceGroup -Syntax
Get-Help New-AzResourceGroup -Examples
Get-Module Az.Resources | Select-Object Name, Version, Path
```

Confirm that the module path and version identify the preview, not a classic installation. If local help doesn't include examples, use the [preview cmdlet reference](/powershell/module/?view=azps-preview&preserve-view=true).

## Create a test resource group

Replace the subscription and location placeholders before running these commands. Use the same session for the remaining examples.

```powershell
$ErrorActionPreference = 'Stop'
$sub = '<test-subscription-id>'
$location = '<region>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$rg = "azclips-recovery-$run"

New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
Get-AzResourceGroup -SubscriptionId $sub -Name $rg
```

## Use authenticated REST

Read the test resource group by using its Azure Resource Manager path. The request uses the preview session's existing authentication.

```powershell
$uri = "/subscriptions/$sub/resourceGroups/${rg}?api-version=2021-04-01"
Invoke-AzRestMethod -Method GET -Uri $uri
```

Inspect the returned HTTP status, headers, and body. Compare the resource name and location with the `Get-AzResourceGroup` result.

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

Use the command name, parameters, and error message to check the preview reference and reproduce the problem. Before sharing diagnostics, redact credentials, access tokens, and sensitive output. Include the PowerShell version and preview module versions.

AI-based error recovery is available in the Azure CLI preview, not the Azure PowerShell preview. Don't run CLI recovery commands as PowerShell cmdlets. For more information, see [AI-based error recovery in Azure CLI preview](/cli/azure/ai-based-error-recovery?view=azure-cli-preview&preserve-view=true).

## Clean up resources

Delete only the test resource group created in this article. Deletion also removes any resources that you added to that group.

```powershell
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Get-AzResourceGroup -SubscriptionId $sub -Name $rg -ErrorAction SilentlyContinue
```

The final lookup should return no group. Check for deletion errors before treating cleanup as complete.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Troubleshooting](troubleshooting.md).
