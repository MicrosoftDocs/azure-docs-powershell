---
title: Manage Azure subscriptions with Azure PowerShell
description: Manage Azure subscriptions with Azure PowerShell
ms.devlang: powershell
ms.topic: conceptual

ms.custom: devx-track-azurepowershell
---

# Manage multiple Azure subscriptions

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

If you're brand new to Azure, you probably only have a single subscription. But if you have been
using Azure for a while, you may have created multiple Azure subscriptions. You can configure Azure
PowerShell to execute commands against a particular subscription.

1. Get a list of all subscriptions in your account.

   ```azurepowershell
   Get-AzureRmSubscription
   ```

   ```Output
   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My Production Subscription
   CurrentStorageAccount :

   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My DevTest Subscription
   CurrentStorageAccount :

   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My Demos
   CurrentStorageAccount :
   ```

2. Set the default.

   ```azurepowershell
   Select-AzureRmSubscription -Subscription 'My Demos'
   ```

3. Verify the change by running the `Get-AzureRmContext` cmdlet.

   ```azurepowershell
   Get-AzureRmContext
   ```

   ```Output
   Environment           : AzureCloud
   Account               : username@contoso.com
   TenantId              : 00000000-0000-0000-0000-000000000000
   SubscriptionId        : 00000000-0000-0000-0000-000000000000
   SubscriptionName      : My Demos
   CurrentStorageAccount :
   ```

Once you set your default subscription, all Azure PowerShell commands run against this
subscription.
