---
title: "Tutorial: Access a Key Vault secret with a managed identity with Azure PowerShell (preview)"
description: "Create a managed identity, grant access to a test Key Vault secret, verify access, and revoke it with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: tutorial
ms.date: 10/27/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Tutorial: Access a Key Vault secret with a managed identity with Azure PowerShell (preview)

In this tutorial, you create a managed identity, grant access to a test Key Vault secret, verify access, and revoke it with Azure PowerShell preview.

In this tutorial, you:

> [!div class="checklist"]
> - Create the application's identity
> - Store a test secret
> - Grant access
> - Read the secret as the application
> - Revoke access
> - Clean up

> [!IMPORTANT]
> These draft examples require end-to-end validation against the release build before use.

> [!WARNING]
> This scenario requires non-interactive authentication that the [current preview limitations](getting-started.md#current-limitations) list as unsupported. Use these commands for engineering review only. They don't establish supported functionality. Don't run this walkthrough until the product team confirms support for your preview build.

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- An Azure host, such as a VM, that can use a user-assigned managed identity and has the Azure CLI preview or modules installed.
- An existing test Key Vault that uses Azure role-based access control and is reachable from that host.
- The role definition ID of a built-in role that grants secret read access, and permission to assign it.

Use only synthetic secret values. Do not print or log secret values.

You need an Azure subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

Allow time for role changes to take effect before verifying a grant or a revocation. The managed-identity sign-in runs on the host, so set the same subscription, vault, secret, client ID and run values there.

## Set variables

```powershell
$ErrorActionPreference = 'Stop'
$sub = '<test-subscription-id>'
$location = '<region>'
$vault = '<existing-test-vault-name>'
$vaultId = '<existing-test-vault-resource-ID>'
$role = '<secret-read-role-definition-ID>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$rg = "azclips-access-$run"
$identity = "app-identity-$run"
$secret = "app-secret-$run"
$assignment = [guid]::NewGuid().ToString()
$psIdentity = @{ SubscriptionId = $sub; ResourceGroupName = $rg; Name = $identity }
```

## Create the application's identity

```powershell
New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
New-AzUserAssignedIdentity @psIdentity -Location $location
$id = Get-AzUserAssignedIdentity @psIdentity
$principalId = $id.Properties.PrincipalId
$clientId = $id.Properties.ClientId
```

## Store a test secret

```powershell
Set-AzKeyVaultSecret -VaultName $vault -Name $secret -SecretValue (ConvertTo-SecureString 'azclips-synthetic' -AsPlainText -Force)
Get-AzKeyVaultSecret -VaultName $vault -Name $secret
```

## Grant access

```powershell
New-AzRoleAssignment -Scope $vaultId -ObjectId $principalId -ObjectType ServicePrincipal -RoleDefinitionId $role -Name $assignment
Get-AzRoleAssignment -Scope $vaultId -ObjectId $principalId
```

Attach the identity to the host: **Pending engineering confirmation: command to attach the identity to the host.**

## Read the secret as the application

On the host:

```powershell
Connect-AzAccount -Identity -ClientId $clientId -SubscriptionId $sub -OutProfile "workload-$run"
$value = Get-AzKeyVaultSecret -VaultName $vault -Name $secret -AsPlainText
if ($value -ne 'azclips-synthetic') { throw 'Secret value mismatch.' }
```

## Revoke access

```powershell
Remove-AzRoleAssignment -Scope $vaultId -Name $assignment
Get-AzRoleAssignment -Scope $vaultId -ObjectId $principalId
```

On the host, repeat the read from [Read the secret as the application](#read-the-secret-as-the-application). Confirm that the read now fails with an access-denied error.

## Clean up resources

Detach the identity from the host: **Pending engineering confirmation: command to detach the identity from the host.**

```powershell
Remove-AzUserAssignedIdentity @psIdentity
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Remove-AzKeyVaultSecret -VaultName $vault -Name $secret -Confirm:$false
Remove-Variable value -ErrorAction SilentlyContinue
```

On the host, sign out and remove the `workload-$run` profile with `Disconnect-AzAccount` and `Remove-AzProfile -Name "workload-$run"`.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Deploy and troubleshoot a Bicep template](tutorial-deploy-bicep.md).
