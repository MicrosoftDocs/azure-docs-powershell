---
title: "Tutorial: Run repeatable deployments from a pipeline with Azure PowerShell (preview)"
description: "Plan federated pipeline authentication, repeat a test deployment, detect a failure, and clean up with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: tutorial
ms.date: 10/28/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Tutorial: Run repeatable deployments from a pipeline with Azure PowerShell (preview)

In this tutorial, you set up a pipeline job that uses Azure PowerShell preview to authenticate without a browser, deploy predictably, and report a failure when a command fails.

By the end of this tutorial, a non-interactive job deploys the intended storage account, a repeat run doesn't create a duplicate, failures are visible in the job, and the job removes its test resources and local sign-in state.

In this tutorial, you:

> [!div class="checklist"]
> - Sign in without a browser
> - Prepare the job
> - Deploy twice
> - Detect a failure
> - Clean up

> [!WARNING]
> This scenario requires non-interactive authentication that the [current preview limitations](getting-started.md#current-limitations) list as unsupported. Use these commands for engineering review only. They don't establish supported functionality. Don't run this walkthrough until the product team confirms support for your preview build.

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- A test pipeline agent with the Azure PowerShell preview, installed as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- A test service principal with least-privilege access to the test subscription and a federated credential for your pipeline provider. The provider supplies a token file whose path is in `AZURE_FEDERATED_TOKEN_FILE`.
- The sample storage template from [Deploy and troubleshoot a Bicep template](tutorial-deploy-bicep.md).

Never print tokens, secrets, or the process environment in job output.

You need an Azure subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

## Set variables

```powershell
$ErrorActionPreference = 'Stop'
$tenant = '<test-tenant-id>'
$sub = '<test-subscription-id>'
$clientId = '<application-client-ID>'
$location = '<region>'
$template = '<path-to-sample-storage.bicep>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$profile = "pipeline-$run"
$rg = "azclips-ci-$run"
$deployment = "ci-$run"
$storage = "clips$([guid]::NewGuid().ToString('N').Substring(0, 18))"
```

## Sign in without a browser

```powershell
$federatedToken = (Get-Content -LiteralPath $env:AZURE_FEDERATED_TOKEN_FILE -Raw).Trim()
Connect-AzAccount -ServicePrincipal -ClientId $clientId -TenantId $tenant -SubscriptionId $sub -FederatedToken $federatedToken -OutProfile $profile
```

`Connect-AzAccount` returns the new profile with the tenant ID and subscription ID that you specified. No browser or device code prompt appears.

## Prepare the job

```powershell
Get-AzProfile -Name $profile
New-AzResourceGroup -SubscriptionId $sub -Name $rg -Location $location
```

`Get-AzProfile` returns the pipeline profile with the expected tenant ID and subscription ID. `New-AzResourceGroup` returns the new resource group with a provisioning state of `Succeeded`.

## Deploy twice

Run the same deployment twice, as a pipeline does when a job is rerun. In Incremental mode, the second run updates the existing storage account to match the template instead of creating another one.

```powershell
$outputs = 1..2 | ForEach-Object {
    New-AzResourceGroupDeployment -SubscriptionId $sub -ResourceGroupName $rg -Name $deployment -TemplateFile $template -Parameter "storageAccountName=$storage" -Mode Incremental | Out-Null
    $result = Get-AzResourceGroupDeployment -SubscriptionId $sub -ResourceGroupName $rg -Name $deployment
    if ($result.ProvisioningState -ne 'Succeeded') { throw "Deployment run $_ didn't succeed." }
    $result.Outputs | ConvertTo-Json -Depth 5
}
if ($outputs[0] -ne $outputs[1]) { throw 'The repeat deployment returned a different storage account ID.' }
```

The check produces no output when both runs succeed and return the same `storageAccountId`. If either run fails or the second run returns a different storage account, the job stops with an error.

## Detect a failure

```powershell
try {
    Get-AzResourceGroup -SubscriptionId $sub -Name "$rg-missing" -ErrorAction Stop
    throw 'Missing-resource lookup unexpectedly succeeded.'
}
catch {
    if ($_.Exception.Message -like '*unexpectedly succeeded*') { throw }
}
```

The lookup fails because the resource group doesn't exist, and the `catch` block handles the expected error, so the step produces no output. In a real job, let unexpected errors stop the job. Because `$ErrorActionPreference` is `Stop`, a failing cmdlet stops the script with an error, and the pipeline reports the step as failed.

## Clean up resources

Configure the pipeline to run cleanup even when an earlier step fails. The examples below show the cleanup commands, not a complete pipeline job or failure-handling wrapper.

```powershell
Remove-AzResourceGroup -SubscriptionId $sub -Name $rg -Force
Get-AzResourceGroup -SubscriptionId $sub -Name $rg -ErrorAction SilentlyContinue
Set-AzProfile -Name $profile
Disconnect-AzAccount
Remove-AzProfile -Name $profile
Remove-Variable federatedToken
```

`Remove-AzResourceGroup` returns `True` when the deletion completes, and the `Get-AzResourceGroup` command returns no output. `Disconnect-AzAccount` and `Remove-AzProfile` don't return output.

## Other sign-in methods

Replace the sign-in example with one of the following. Keep secrets and certificates in the pipeline's secret store, never in source or job output.

**Managed identity**, on an agent with an assigned managed identity. Set the client ID to the managed identity's client ID.

- Azure PowerShell preview: `Connect-AzAccount -Identity -ClientId $clientId -SubscriptionId $sub -OutProfile $profile`

**Client secret or certificate**

- Azure PowerShell preview: **Pending engineering confirmation: client-secret or certificate sign-in command.**

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Discover commands and recover from failures](how-to-command-recovery.md).
