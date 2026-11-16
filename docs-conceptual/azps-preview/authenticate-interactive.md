---
title: Sign in to Azure PowerShell (preview) interactively
description: Learn how to sign in to the Azure PowerShell preview interactively with Connect-AzAccount, save the sign-in as a profile, refresh it, and sign out.
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: how-to
ms.date: 11/16/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-generated
---

# Sign in to Azure PowerShell (preview) interactively

Interactive sign-in is the recommended way to authenticate with the Azure PowerShell preview. You run `Connect-AzAccount`, complete sign-in in your browser, and the preview saves the result as a _profile_: a sign-in context that stores your tenant, subscription, cloud, and identity.

This article shows how to sign in interactively, save and refresh a profile, and sign out.

## Prerequisites

- Azure PowerShell preview, installed. Use a PowerShell 7.6 or later session without classic Az modules loaded. For more information, see [Install the Azure PowerShell preview](install-azure-powershell.md).
- An Azure account with access to at least one subscription. If you don't have one, [create a free account](https://azure.microsoft.com/free/).
- The tenant ID and subscription ID that you want to use. To find them, go to the Azure portal, select **Subscriptions**, select the subscription, and then review **Overview**.

## Sign in

Run `Connect-AzAccount` with the tenant and subscription you want to work in. You must specify a subscription ID the first time you sign in:

```powershell
Connect-AzAccount -TenantId <tenant-id> -SubscriptionId <subscription-id>
```

Azure PowerShell opens your default browser. After you complete sign-in, Azure PowerShell saves the sign-in context in the reserved `default` profile. Later commands run in that tenant and subscription.

The preview doesn't share sign-in state with classic Azure PowerShell or with Azure CLI. Sign in separately to each tool that you use.

## Save the sign-in as a named profile

To keep a sign-in that you can switch back to later, add `-OutProfile` with a profile name:

```powershell
Connect-AzAccount -TenantId <tenant-id> -SubscriptionId <subscription-id> -OutProfile dev
```

The new profile becomes the active profile. Use a separate profile for each tenant or subscription that you work in, and then switch between them with `Set-AzProfile`. For a walkthrough, see [Quickstart: Set up and switch sign-in profiles](quickstart-profiles.md).

## Sign in without a browser

If a browser isn't available on the machine, for example in an SSH session or a container, add `-UseDeviceCode`. Azure PowerShell displays a code and a URL. Open the URL on another device, enter the code, and complete sign-in there. Use browser sign-in whenever it's available.

## Check which account you're using

To see the tenant, subscription, and identity that commands use, get the active profile:

```powershell
Get-AzProfile -Active
```

## Refresh an expired sign-in

If the sign-in for a profile expires, sign in again with `-Profile` to refresh that profile in place. Azure PowerShell uses the subscription saved in the profile:

```powershell
Connect-AzAccount -Profile dev
```

You can't combine `-Profile` with `-OutProfile` or `-SubscriptionId`. Use `-OutProfile` to create or overwrite a profile, and `-Profile` to refresh an existing one.

## Sign out

To sign out of the active profile and clear its account from the token cache, run `Disconnect-AzAccount`:

```powershell
Disconnect-AzAccount
```

To remove a saved profile entirely, use `Remove-AzProfile -Name <profile-name>`.

## Related content

- For more information, see [Manage sign-in profiles](authenticate-azureps.md).
- For more information, see [Quickstart: Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Get started with Azure PowerShell (preview)](get-started-azureps.md).
