---
title: Manage Azure subscriptions with Azure PowerShell
description: Manage Azure subscriptions with Azure PowerShell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/30/2017 
ms.custom: devx-track-azurepowershell
---
# Manage multiple Azure subscriptions

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

If you are brand new to Azure, you probably only have a single subscription. But if you have been
using Azure for a while, you may have created multiple Azure subscriptions. You can configure Azure
PowerShell to execute commands against a particular subscription.

1. Get a list of all subscriptions in your account.

    ```azurepowershell-interactive
    Get-AzureRmSubscription
    ```

    ```output
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :

    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My DevTest Subscription
    CurrentStorageAccount :

    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Demos
    CurrentStorageAccount :
    ```

2. Set the default.

    ```azurepowershell-interactive
    Select-AzureRmSubscription -SubscriptionName "My Demos"
    ```

3. Verify the change by running the `Get-AzureRmContext` cmdlet.

    ```azurepowershell-interactive
    Get-AzureRmContext
    ```

    ```output
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Demos
    CurrentStorageAccount :
    ```

Once you set your default subscription, all subsequent Azure PowerShell commands run against this
subscription.
