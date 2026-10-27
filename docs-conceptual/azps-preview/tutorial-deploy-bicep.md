---
title: "Tutorial: Deploy and troubleshoot a Bicep template with Azure PowerShell (preview)"
description: "Preview and deploy a Bicep template, repeat the deployment, investigate an error, and clean up with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: tutorial
ms.date: 10/27/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Tutorial: Deploy and troubleshoot a Bicep template with Azure PowerShell (preview)

In this tutorial, you preview and deploy a Bicep template, repeat the deployment, investigate an error, and clean up with Azure PowerShell preview.

In this tutorial, you:

> [!div class="checklist"]
> - Prepare the deployment
> - Preview the change
> - Deploy and inspect
> - Repeat the deployment
> - Diagnose a failure
> - Clean up

> [!IMPORTANT]
> These draft examples require end-to-end validation against the release build before use.

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

## Preview the change

```powershell
New-AzResourceGroupDeploymentWhatIf @psDeployment -TemplateFile $template -Parameter "storageAccountName=$storage" -Mode Incremental
```

## Deploy and inspect

```powershell
New-AzResourceGroupDeployment @psDeployment -TemplateFile $template -Parameter "storageAccountName=$storage" -ValidationLevel Provider -Mode Incremental
Get-AzResourceGroupDeployment @psDeployment
```

## Repeat the deployment

```powershell
New-AzResourceGroupDeployment @psDeployment -TemplateFile $template -Parameter "storageAccountName=$storage" -ValidationLevel Provider -Mode Incremental
```

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

Inspect the deployment operations: **Pending engineering confirmation: deployment operations command.**

## Clean up resources

```powershell
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Get-AzResourceGroup -SubscriptionId $sub -Name $rg -ErrorAction SilentlyContinue
```

## Other deployment scopes

Repeat the preview, deploy, inspect and clean-up steps at a broader scope, using a template written for that scope. Use test scopes and uniquely named resources. Deleting the resource group does not remove resources deployed at a higher scope, so remove those resources individually.

- Subscription scope: **Pending engineering confirmation: subscription deployment commands.**
- Management group scope: **Pending engineering confirmation: management group deployment commands.**
- Tenant scope: **Pending engineering confirmation: tenant deployment commands.**

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Store and retrieve application data](tutorial-storage-data.md).
