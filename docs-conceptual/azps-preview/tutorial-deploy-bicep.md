---
title: "Tutorial: Deploy and troubleshoot a Bicep template with Azure PowerShell (preview)"
description: "Preview and deploy a Bicep template, repeat the deployment, investigate an error, and clean up with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: tutorial
ms.date: 10/28/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Tutorial: Deploy and troubleshoot a Bicep template with Azure PowerShell (preview)

In this tutorial, you use Azure PowerShell preview to preview an infrastructure change, deploy it, understand a failure, and remove the test environment.

By the end of this tutorial, a Bicep template creates one storage account, a repeat deployment leaves that same storage account in place instead of creating another one, and a controlled failure returns an error message you can act on. You then delete every resource that the tutorial created.

In this tutorial, you:

> [!div class="checklist"]
> - Prepare the deployment
> - Preview the change
> - Deploy and inspect
> - Repeat the deployment
> - Diagnose a failure
> - Clean up

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- The Bicep CLI, and the sample storage template in [Create the Bicep template](#create-the-bicep-template) saved locally.

Deploy in Incremental mode into a dedicated resource group, not against shared resources.

You need an Azure subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

## Create the Bicep template

Save the following resource-group-scoped template as `sample-storage.bicep`. Set the template path in the next section to this local file. The template disables anonymous blob access and shared-key authorization and requires HTTPS with TLS 1.2 or later.

```bicep
targetScope = 'resourceGroup'

@description('Globally unique storage account name.')
param storageAccountName string

@description('Storage account location.')
param location string = resourceGroup().location

resource storageAccount 'Microsoft.Storage/storageAccounts@2023-01-01' = {
  name: storageAccountName
  location: location
  sku: {
    name: 'Standard_LRS'
  }
  kind: 'StorageV2'
  properties: {
    minimumTlsVersion: 'TLS1_2'
    supportsHttpsTrafficOnly: true
    allowBlobPublicAccess: false
    allowSharedKeyAccess: false
  }
}

output storageAccountId string = storageAccount.id
```

## Set variables

```powershell
$ErrorActionPreference = 'Stop'
$sub = '<test-subscription-id>'
$location = '<region>'
$template = '<path-to-sample-storage.bicep>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$rg = "azclips-iac-$run"
$deployment = "deploy-$run"
$storage = "clips$([guid]::NewGuid().ToString('N').Substring(0, 18))"
$psDeployment = @{ SubscriptionId = $sub; ResourceGroupName = $rg; Name = $deployment }
```

## Prepare the deployment

```powershell
New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
Set-AzResourceGroup -SubscriptionId $sub -Name $rg -Tag @{ purpose = 'iac-review' }
Get-AzResourceGroup -SubscriptionId $sub -Name $rg
```

`Set-AzResourceGroup` replaces all tags on the resource group with the tags that you supply, so include any tags that you want to keep. The final command returns the resource group with a provisioning state of `Succeeded` and the tag `purpose` set to `iac-review`.

## Preview the change

```powershell
New-AzResourceGroupDeploymentWhatIf @psDeployment -TemplateFile $template -Parameter "storageAccountName=$storage" -Mode Incremental
```

What-if doesn't create or change any resources. Because the resource group is empty, the result lists one change: a `Create` for the `Microsoft.Storage/storageAccounts` resource with the name in `$storage`. If the result lists other changes, stop and review the template before you deploy.

## Deploy and inspect

```powershell
New-AzResourceGroupDeployment @psDeployment -TemplateFile $template -Parameter "storageAccountName=$storage" -ValidationLevel Provider -Mode Incremental
$first = Get-AzResourceGroupDeployment @psDeployment
$first.ProvisioningState
$first.Outputs | ConvertTo-Json -Depth 5
```

The deployment's provisioning state is `Succeeded`. The outputs include `storageAccountId`, the resource ID of the new storage account, which ends with `/providers/Microsoft.Storage/storageAccounts/<storage-account-name>`.

## Repeat the deployment

Run the same deployment again to confirm that it's repeatable. In Incremental mode, Azure Resource Manager compares the template with the resources that already exist and updates them to match. Because the storage account already matches the template, the repeat deployment doesn't create a second storage account.

```powershell
New-AzResourceGroupDeployment @psDeployment -TemplateFile $template -Parameter "storageAccountName=$storage" -ValidationLevel Provider -Mode Incremental
$second = Get-AzResourceGroupDeployment @psDeployment
$second.ProvisioningState
if (($first.Outputs | ConvertTo-Json -Depth 5) -ne ($second.Outputs | ConvertTo-Json -Depth 5)) {
    throw 'The repeat deployment returned a different storage account ID.'
}
```

The provisioning state is `Succeeded` again, and the check produces no output, because both deployments return the same `storageAccountId`.

## Diagnose a failure

```powershell
try {
    New-AzResourceGroupDeployment -SubscriptionId $sub -ResourceGroupName $rg -Name "$deployment-invalid" -TemplateFile $template -Parameter "storageAccountName=$storage" -Mode Foo
    throw 'The invalid deployment unexpectedly succeeded.'
}
catch {
    if ($_.Exception.Message -like '*unexpectedly succeeded*') { throw }
    $_.Exception.Message
}
```

`Foo` isn't a valid deployment mode, so the deployment is rejected. The output is the error message that explains why the request was rejected. Use the message to correct the command before you retry it.

Inspect the deployment operations: **Pending engineering confirmation: deployment operations command.**

## Clean up resources

```powershell
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Get-AzResourceGroup -SubscriptionId $sub -Name $rg -ErrorAction SilentlyContinue
```

`Remove-AzResourceGroup` deletes the resource group, the storage account, and the deployment history, and returns `True` when the deletion completes. The `Get-AzResourceGroup` command then returns no output.

## Other deployment scopes

Repeat the preview, deploy, inspect and clean-up steps at a broader scope, using a template written for that scope. Use test scopes and uniquely named resources. Deleting the resource group doesn't remove resources deployed at a higher scope, so remove those resources individually.

- Subscription scope: **Pending engineering confirmation: subscription deployment commands.**
- Management group scope: **Pending engineering confirmation: management group deployment commands.**
- Tenant scope: **Pending engineering confirmation: tenant deployment commands.**

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Run repeatable deployments from a pipeline](tutorial-pipeline-deployments.md).
