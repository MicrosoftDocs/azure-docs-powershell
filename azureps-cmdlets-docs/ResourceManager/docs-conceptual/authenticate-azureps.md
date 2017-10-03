---
title: Log in with Azure PowerShell
description: Log in with Azure PowerShell
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
---

# Log in with Azure PowerShell

Azure PowerShell supports multiple login methods. The simplest way to get started is to log in
interactively at the command line.

## Interactive log in

1. Type `Login-AzureRmAccount`. You will get dialog box asking for your Azure credentials.

2. Type the email address and password associated with your account. Azure authenticates and saves
   the credential information, and then closes the window.

## Log in with a service principal

Service principals provide a way for you to create non-interactive accounts that you can use to
manipulate resources. Service principals are like user accounts to which you can apply rules using
Azure Active Directory. By granting the minimum permissions needed to a service principal, you can
ensure your automation scripts are even more secure.

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

### Log in using an Azure VM Managed Service Identity

Managed Service Identity (MSI) is a preview feature of Azure Active Directory. You can use an MSI
service principal for sign-in, and acquire an app-only access token to access other resources.

For more information about MSI, see
[How to use an Azure VM Managed Service Identity (MSI) for sign-in and token acquisition](/azure/active-directory/msi-how-to-get-access-token-using-msi).

## Log in to another Cloud

Azure cloud services provide different environments that adhere to the data-handling regulations of
various governments. If your Azure account is in one the government clouds, you need to specify the
environment when you sign in. For example, if you account is in the China cloud you sign on using
the following command:

```powershell
Login-AzureRmAccount -EnvironmentName AzureChinaCloud
```

Use the following command to get a list of available environments:

```powershell
Get-AzureRmEnvironment | Select-Object Name
```

```
Name
----
AzureCloud
AzureChinaCloud
AzureUSGovernment
AzureGermanCloud
```

## Learn more about managing Azure role-based access

For more information about authentication and subscription management in Azure, see
[Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).

Azure PowerShell cmdlets for role management

* [Get-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [Get-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [New-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [New-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [Remove-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [Remove-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [Set-AzureRmRoleDefinition](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)
