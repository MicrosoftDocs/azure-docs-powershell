---
title: "Quickstart: Set up and switch sign-in profiles with Azure PowerShell (preview)"
description: "Set up named sign-in profiles for two subscriptions, switch between them, and remove the test profiles with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: quickstart
ms.date: 10/28/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Quickstart: Set up and switch sign-in profiles with Azure PowerShell (preview)

In this quickstart, you set up Azure PowerShell preview next to your existing Azure PowerShell modules, and then use named sign-in profiles to move between two subscriptions without signing in again each time.

By the end of this quickstart, you:

- Confirm that the preview modules are loaded, and know how to switch between the classic modules and the preview.
- Save two named sign-in profiles, one for each subscription, and confirm that each profile selects the intended tenant and subscription.
- Remove the test profiles and restore the profile you started with, if you had one.

## Prerequisites

- Azure PowerShell preview, installed by following [Install Azure PowerShell preview](install-overview.md).
- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- A workstation with a default browser for interactive sign-in.
- Two Azure subscriptions you can sign in to. The subscriptions can be in the same tenant or in different tenants. If you don't have a subscription, [create a free account](https://azure.microsoft.com/free/).

To find each subscription ID and its directory (tenant) ID, go to the Azure portal, select **Subscriptions**, select the subscription, and then review **Overview**. If both subscriptions are in the same directory, use the same tenant ID for both.

## Verify the installation

Load the newest installed preview, and then confirm that the cmdlets come from the preview modules.

```powershell
Import-Module Az -MinimumVersion 0.1.1 -MaximumVersion 0.1.9999
Get-Command Connect-AzAccount, Get-AzResourceGroup
Get-Module Az.Accounts, Az.Resources | Select-Object Name, Version, Path
```

`Get-Command` lists both cmdlets with `Az.Accounts` and `Az.Resources` as their source. `Get-Module` shows a version in the `0.1.x` series for both modules, and a path in your preview installation. A higher version, such as `16.4.0`, means that the classic modules are loaded instead. In that case, start a new session and load the preview again.

## Switch between classic and preview

A PowerShell session can load only one version of the Az modules, so you switch by starting a new session. If you have classic Azure PowerShell installed, start a child session that loads the classic modules and check their version:

```powershell
pwsh -NoExit -Command 'Import-Module Az; Get-Module Az | Select-Object Name, Version'
```

The output shows a classic version, such as `16.4.0`. Run `exit` to close the child session. In your original session, confirm that the preview is still loaded:

```powershell
Get-Module Az.Accounts | Select-Object Name, Version
```

A `0.1.x` version means the preview is active. For more information, see [Switch between classic and preview Azure PowerShell](switch-azps-versions.md).

## Set variables

Replace the placeholders with your values. The script also records the profile that's active now, if any, so that you can restore it when you finish. If you've never used Azure PowerShell preview, there's no active profile and the variable stays empty.

```powershell
$ErrorActionPreference = 'Stop'
$tenantA = '<tenant-A-id>'
$subA = '<subscription-A-id>'
$tenantB = '<tenant-B-id>'
$subB = '<subscription-B-id>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$profileA = "review-a-$run"
$profileB = "review-b-$run"
$previousProfile = $null
try { $previousProfile = (Get-AzProfile -Active).Name } catch { }
"Previous profile: $(if ($previousProfile) { $previousProfile } else { '<none>' })"
```

The last line shows the name of your current active profile, or `<none>`.

## Save two sign-in contexts

Sign in once for each subscription. Each command opens your browser for an interactive sign-in and saves the result as a new named profile.

```powershell
Connect-AzAccount -TenantId $tenantA -SubscriptionId $subA -OutProfile $profileA
Connect-AzAccount -TenantId $tenantB -SubscriptionId $subB -OutProfile $profileB
```

After each sign-in, the output shows the profile name, tenant ID, and subscription ID that you specified.

## Switch work environments

List your profiles, and then switch between them and list the resource groups in each subscription.

```powershell
Get-AzProfile
Get-AzProfile -Name $profileA
Set-AzProfile -Name $profileA
Get-AzResourceGroup
Set-AzProfile -Name $profileB
Get-AzResourceGroup
Get-AzProfile -Active
```

`Get-AzProfile` lists both new profiles. Each `Set-AzProfile` command returns the profile that it activated, with that profile's tenant ID and subscription ID. Each `Get-AzResourceGroup` command lists the resource groups in the subscription for the active profile, so the two lists differ unless both subscriptions contain the same groups. `Get-AzProfile -Active` returns the second profile, because you switched to it last.

`Set-AzProfile` doesn't sign in again. If a saved sign-in expires, run `Connect-AzAccount -Profile <profile-name>` to refresh it.

## Clean up resources

Sign out of each test profile and remove it. Then restore the profile that was active when you started, if there was one.

```powershell
foreach ($p in $profileA, $profileB) {
    Set-AzProfile -Name $p
    Disconnect-AzAccount
    Remove-AzProfile -Name $p
}
if ($previousProfile) {
    Set-AzProfile -Name $previousProfile
}
else {
    'No previous profile to restore.'
}
Get-AzProfile
```

`Disconnect-AzAccount` and `Remove-AzProfile` don't return output. The final `Get-AzProfile` command no longer lists the test profiles. If you had a previous profile, `Set-AzProfile` returns it as the active profile.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Manage sign-in profiles in Azure PowerShell](profile-base-login.md).
- For more information, see [Deploy and manage a virtual machine application](tutorial-vm-application.md).
