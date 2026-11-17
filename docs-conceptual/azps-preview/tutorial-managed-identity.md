---
title: "Tutorial: Access a Key Vault secret with a managed identity with Azure PowerShell (preview)"
description: "Create a managed identity, grant access to a test Key Vault secret, verify access, and revoke it with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: tutorial
ms.date: 11/16/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Tutorial: Access a Key Vault secret with a managed identity with Azure PowerShell (preview)

In this tutorial, you give an application access to a Key Vault secret by using a managed identity instead of an embedded password.

By the end of this tutorial, a workload reads a test secret by using its assigned identity, loses access after you revoke the role assignment, and leaves no test identity or active test secret behind.

In this tutorial, you:

> [!div class="checklist"]
> - Create the application's identity
> - Store a test secret
> - Grant access
> - Attach the identity to the VM
> - Read the secret as the application
> - Revoke access
> - Clean up

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- A test Azure VM to run the workload, with Azure PowerShell preview installed and no managed identities assigned. You need permission to update the VM, such as the Virtual Machine Contributor role.
- An existing test Key Vault that uses Azure role-based access control and is reachable from that VM. To find the vault's resource ID, go to the Azure portal, open the key vault, and then select **Settings** > **Properties**.
- The role definition ID of a built-in role that grants secret read access, such as Key Vault Secrets User (`4633458b-17de-408a-b874-0445c86b69e6`), and permission to assign it.

Use only synthetic secret values. Don't print or log secret values.

You need an Azure subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

Allow time for role changes to take effect before verifying a grant or a revocation. The managed-identity sign-in runs on the VM, so set the same subscription, vault, secret, client ID, and run values there.

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
$identityId = "/subscriptions/$sub/resourceGroups/$rg/providers/Microsoft.ManagedIdentity/userAssignedIdentities/$identity"
$vmId = '<test-VM-resource-ID>'
```

## Create the application's identity

```powershell
New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
New-AzUserAssignedIdentity @psIdentity -Location $location
$id = Get-AzUserAssignedIdentity @psIdentity
$principalId = $id.Properties.PrincipalId
$clientId = $id.Properties.ClientId
```

`New-AzUserAssignedIdentity` returns the new identity. The `$principalId` and `$clientId` variables now hold the identity's principal (object) ID and client ID as GUIDs.

## Store a test secret

```powershell
Set-AzKeyVaultSecret -VaultName $vault -Name $secret -SecretValue (ConvertTo-SecureString 'azclips-synthetic' -AsPlainText -Force)
Get-AzKeyVaultSecret -VaultName $vault -Name $secret
```

Both commands return the secret's identifier and attributes, such as whether it's enabled. They don't return the secret value.

## Grant access

```powershell
New-AzRoleAssignment -Scope $vaultId -ObjectId $principalId -ObjectType ServicePrincipal -RoleDefinitionId $role -Name $assignment
Get-AzRoleAssignment -Scope $vaultId -ObjectId $principalId
```

`New-AzRoleAssignment` returns the new role assignment, including its role definition ID, principal ID, and scope. `Get-AzRoleAssignment` returns that same assignment.

## Attach the identity to the VM

> [!NOTE]
> The Azure PowerShell preview doesn't include cmdlets to attach a managed identity to a VM or detach it. This step, and the matching step in [Clean up resources](#clean-up-resources), use `Invoke-AzRestMethod` to send the Azure Resource Manager request directly. All other steps use dedicated preview cmdlets.

Assign the user-assigned identity to the VM with a `PATCH` request to the [Virtual Machines - Update](/rest/api/compute/virtual-machines/update) API:

```powershell
$body = @{ identity = @{ type = 'UserAssigned'; userAssignedIdentities = @{ $identityId = @{} } } } | ConvertTo-Json -Depth 4 -Compress
Invoke-AzRestMethod -Method PATCH -Uri "${vmId}?api-version=2026-04-01" -Payload $body -Headers @{ 'Content-Type' = 'application/json' }
```

The response shows status code `200`, and its body is the updated VM, with the identity's resource ID listed under `identity.userAssignedIdentities`. `Invoke-AzRestMethod` doesn't wait for long-running operations, so if the body shows a `provisioningState` of `Updating`, wait a minute before you continue. This request sets the VM's identity type to `UserAssigned`, which replaces any other identity configuration, so use a test VM that has no other managed identities.

## Read the secret as the application

On the VM:

```powershell
Connect-AzAccount -Identity -ClientId $clientId -SubscriptionId $sub -OutProfile "workload-$run"
$value = Get-AzKeyVaultSecret -VaultName $vault -Name $secret -AsPlainText
if ($value -ne 'azclips-synthetic') { throw 'Secret value mismatch.' }
```

`Connect-AzAccount` returns the new profile with your subscription ID. If the identity reads the expected value, the check produces no output. Otherwise, it stops with `Secret value mismatch.`

## Revoke access

```powershell
Remove-AzRoleAssignment -Scope $vaultId -Name $assignment
Get-AzRoleAssignment -Scope $vaultId -ObjectId $principalId
```

`Remove-AzRoleAssignment` returns the deleted assignment. `Get-AzRoleAssignment` then returns no output, because the identity no longer has an assignment at the vault scope.

On the VM, repeat the read from [Read the secret as the application](#read-the-secret-as-the-application). Confirm that the read now fails with an access-denied (`Forbidden`) error.

## Clean up resources

Detach the identity from the VM. Like the attach step, this step uses `Invoke-AzRestMethod` because the preview has no cmdlet for it. Setting the identity type to `None` removes all managed identities from the VM.

```powershell
Invoke-AzRestMethod -Method PATCH -Uri "${vmId}?api-version=2026-04-01" -Payload '{"identity": {"type": "None"}}' -Headers @{ 'Content-Type' = 'application/json' }
```

Then delete the test resources:

```powershell
Remove-AzUserAssignedIdentity @psIdentity
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Remove-AzKeyVaultSecret -VaultName $vault -Name $secret -Confirm:$false
Remove-Variable value -ErrorAction SilentlyContinue
```

`Remove-AzResourceGroup` returns `True` when the resource group is deleted. `Remove-AzKeyVaultSecret` returns metadata for the deleted secret, such as its recovery ID. The secret is soft-deleted and stays recoverable until the vault's retention period ends.

On the VM, sign out and remove the `workload-$run` profile with `Disconnect-AzAccount` and `Remove-AzProfile -Name "workload-$run"`.

## Related content

- For more information, see [Get started with the preview](get-started-azureps.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Deploy and troubleshoot a Bicep template](tutorial-deploy-bicep.md).
