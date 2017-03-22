---
title: Log in with Azure PowerShell
description: Log in with Azure PowerShell
services: azure
author: sdwheeler
manager: carmonm
ms.assetid: 02b18f6b-8bc5-44b2-abbb-4ef7bedb2964
ms.product: azure
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.date: 03/22/2017
ms.author: sewhee
---

# Log in with Azure PowerShell

There are several ways to log in and authenticate with the Azure PowerShell. The simplest way to
get started is to log in interactively at the command line.

## Interactive log in

1. Type `Login-AzureRmAccount`

2. Type the email address and password associated with your account. Azure authenticates and saves
   the credential information, and then closes the window.

## Non-interactive log in

Log in using your work or school account:

```powershell
$cred = Get-Credential
Login-AzureRmAccount -Credential $cred
```

> [!NOTE]
> This non-interactive log in method only works with a work or school account. A work or
> school account is a user that is managed by your work or school, and defined in the Azure Active
> Directory instance for your work or school.
>
> For more information on signing up for Microsoft Azure with a work or school account, see
[How to get an Azure Active Directory tenant](/azure/active-directory/develop/active-directory-howto-tenant).

Once you have authenticated, you are connected to your default subscription. If you have more than
one subscription, you should [confirm your default subscription](manage-subscriptions-azureps.md)
and change to appropriate subscription. For more information, see
[Manage Azure subscriptions with Azure PowerShell](manage-subscriptions-azureps.md).

## Log in with a service principal

The recommended approach is to use service principals, which provide a way for you to create
non-interactive accounts that you can use to manipulate resources. Service principals are like user
accounts to which you can apply rules using Azure Active Directory. By granting the minimum
permissions needed to a service principal, you can ensure your automation scripts are even more
secure.

1. If you don't already have a service principal, [create one](create-azure-service-principal-azureps.md).

2. Log in with the service principal.

    ```powershell
    Login-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
    ```

    To get your TenantId, log in interactively and then get the TenantId from your subscription.

    ```powershell
    Get-AzureRmSubscription
    ```

    ```
    Environment           : AzureCloud
    Account               : username@contoso.com
    TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
    SubscriptionName      : My Production Subscription
    CurrentStorageAccount :
    ```

## Learn more about managing Azure role-based access

For more information about authentication and subscription management in Azure, see
[Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure.md).

Azure PowerShell cmdlets for role management

* [Get-AzureRmRoleAssignment](../ref/Get-AzureRmRoleAssignment.md)
* [Get-AzureRmRoleDefinition](../ref/Get-AzureRmRoleDefinition.md)
* [New-AzureRmRoleAssignment](../ref/New-AzureRmRoleAssignment.md)
* [New-AzureRmRoleDefinition](../ref/New-AzureRmRoleDefinition.md)
* [Remove-AzureRmRoleAssignment](../ref/Remove-AzureRmRoleAssignment.md)
* [Remove-AzureRmRoleDefinition](../ref/Remove-AzureRmRoleDefinition.md)
* [Set-AzureRmRoleDefinition](../ref/Set-AzureRmRoleDefinition.md)