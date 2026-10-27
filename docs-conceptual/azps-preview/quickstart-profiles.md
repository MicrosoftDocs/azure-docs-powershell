---
title: "Quickstart: Set up and switch sign-in profiles with Azure PowerShell (preview)"
description: "Set up named sign-in profiles, switch tenants and subscriptions, and remove test profiles with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: quickstart
ms.date: 10/27/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Quickstart: Set up and switch sign-in profiles with Azure PowerShell (preview)

In this quickstart, you set up named sign-in profiles, switch tenants and subscriptions, and remove test profiles with Azure PowerShell preview.

> [!IMPORTANT]
> These draft examples require end-to-end validation against the release build before use.

## Prerequisites

- Azure PowerShell preview, installed by following [Install Azure PowerShell preview](install-overview.md).
- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Two Azure subscriptions or accounts you can sign in to. They can belong to the same tenant.

Find each subscription ID and its directory (tenant) ID in **Azure portal > Subscriptions > select the subscription > Overview**. Use the same tenant ID twice if both subscriptions are in one directory.

You need an Azure subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).

Before saving the sign-in contexts, note your active profile with `Get-AzProfile -Active`, and do not overwrite existing profiles.

## Set variables

Run this path in a fresh PowerShell 7.6+ session with no classic Az modules loaded.

```powershell
$ErrorActionPreference = 'Stop'
$tenantA = '<tenant-A-id>'
$subA = '<subscription-A-id>'
$tenantB = '<tenant-B-id>'
$subB = '<subscription-B-id>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$profileA = "review-a-$run"
$profileB = "review-b-$run"
```

## Verify the installation

```powershell
Import-Module Az.Accounts -RequiredVersion $previewVersion
Import-Module Az.Resources -RequiredVersion $previewVersion
Get-Command Connect-AzAccount, Get-AzResourceGroup
Get-Module Az.Accounts, Az.Resources | Select-Object Name, Version, Path
```

## Save two sign-in contexts

```powershell
Connect-AzAccount -TenantId $tenantA -SubscriptionId $subA -OutProfile $profileA
Connect-AzAccount -UseDeviceCode -TenantId $tenantB -SubscriptionId $subB -OutProfile $profileB
```

## Switch work environments

```powershell
Get-AzProfile
Get-AzProfile -Name $profileA
Set-AzProfile -Name $profileA
Get-AzResourceGroup
Set-AzProfile -Name $profileB
Get-AzResourceGroup
Get-AzProfile -Active
```

## Refresh and retrieve a token (optional)

```powershell
Connect-AzAccount -Profile $profileA
$tokenResponse = Get-AzAccessToken
if (-not $tokenResponse) { throw 'No token response returned.' }
Remove-Variable tokenResponse
```

Don't print, log, or share access tokens.

## Clean up resources

```powershell
foreach ($p in $profileA, $profileB) {
    Set-AzProfile -Name $p
    Disconnect-AzAccount
    Remove-AzProfile -Name $p
}
```

Restore your previous profile with `Set-AzProfile -Name <previous-profile>`.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Deploy and manage a virtual machine application](tutorial-vm-application.md).
