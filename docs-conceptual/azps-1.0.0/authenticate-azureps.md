---
title: Sign in with Azure PowerShell
description: How to sign in with Azure PowerShell as a user, service principal, or with managed identities for Azure resources.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/29/2018
---
# Sign in with Azure PowerShell

Azure PowerShell supports several authentication methods. The simplest way to get started is to sign in
interactively at the command line.

## Sign in interactively

To sign in interactively, use the [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount) cmdlet.

```azurepowershell-interactive
Connect-AzAccount
```

When run, this cmdlet will present a token string. To log in, copy this string and paste it into https://microsoft.com/devicelogin in a browser. Your PowerShell session will
then be authenticated to connect to Azure. This authentication lasts for the current PowerShell session.

> [!IMPORTANT]
>
> Your credentials are shared among multiple PowerShell sessions as long as you remain signed in.
> For more information, see the article on [Persistent Credentials](context-persistence.md).

## Sign in with a service principal

Service principals are non-interactive Azure accounts. Like other user accounts, their permissions are managed with Azure Active Directory. By granting a service principal only the permissions it needs, your automation scripts stay secure.

To learn how to create a service principal for use with Azure PowerShell, see [Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md).

To sign in with a service principal, use the `-ServicePrincipal` argument with the `Connect-AzAccount` cmdlet. You'll also need the service principal's application ID,
sign-in credentials, and the tenant ID associate with the service principal. To get the service principal's credentials as the appropriate object, use the [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential) cmdlet. This cmdlet will present a prompt for the service principal user ID and password.

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
```

## Sign in using an Azure Managed Service Identity

Managed identities for Azure resources is a feature of Azure Active Directory. You can use a managed identity
service principal for sign-in, and acquire an app-only access token to access other resources. Managed identities are only available on
virtual machines running in an Azure cloud.

For more information about managed identities for Azure resources, see
[How to use managed identities for Azure resources on an Azure VM to acquire an access token](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token).

## Sign in as a Cloud Solution Provider (CSP)

A [Cloud Solution Provider (CSP)](https://azure.microsoft.com/en-us/offers/ms-azr-0145p/) sign-in requires the use of `-TenantId`. Normally, this parameter can be provided as either a tenant ID or a domain name. However, for CSP sign-in, it must be provided a **tenant ID**.

```azurepowershell-interactive
Connect-AzAccount -TenantId 'xxxx-xxxx-xxxx-xxxx'
```

## Sign in to another Cloud

Azure cloud services offer environments compliant with regional data-handling regulations.
For accounts in a regional cloud, set the environment when you sign in with the `-Environment` argument.
For example, if your account is in the China cloud:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

The following command gets a list of available environments:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object Name
```

## Learn more about managing Azure role-based access

For more information about authentication and subscription management in Azure, see
[Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).

Azure PowerShell cmdlets for role management:

* [Get-AzRoleAssignment](/powershell/module/az.Resources/Get-azRoleAssignment)
* [Get-AzRoleDefinition](/powershell/module/az.Resources/Get-azRoleDefinition)
* [New-AzRoleAssignment](/powershell/module/az.Resources/New-azRoleAssignment)
* [New-AzRoleDefinition](/powershell/module/az.Resources/New-azRoleDefinition)
* [Remove-AzRoleAssignment](/powershell/module/az.Resources/Remove-azRoleAssignment)
* [Remove-AzRoleDefinition](/powershell/module/az.Resources/Remove-azRoleDefinition)
* [Set-AzRoleDefinition](/powershell/module/az.Resources/Set-azRoleDefinition)
