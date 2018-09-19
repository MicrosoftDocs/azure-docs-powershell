---
title: Sign in with Azure PowerShell
description: How to sign in with Azure PowerShell as a user, service principal, or with managed identities for Azure resources.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/09/2018
---
# Sign in with Azure PowerShell

Azure PowerShell supports several authentication methods. The simplest way to get started is to sign in
interactively at the command line.

## Sign in interactively

To sign in interactively, use the [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount) cmdlet.

```azurepowershell
Connect-AzureRmAccount
```

When run, this cmdlet will bring up a dialog box prompting you for your email address and password associated with your Azure account. This authentication lasts for the current PowerShell session.

> [!IMPORTANT]
> As of Azure PowerShell 6.3.0, your credentials are shared among multiple PowerShell sessions as long as you remain
> signed in to Windows. For more information, see the article on [Persistent Credentials](context-persistence.md).

## Sign in with a service principal

Service principals are non-interactive Azure accounts. Like other user accounts, their permissions are managed with Azure Active Directory. By granting a service principal only the permissions it needs, your automation scripts
stay secure.

To learn how to create a service principal for use with Azure PowerShell, see [Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md).

To sign in with a service principal, use the `-ServicePrincipal` argument with the `Connect-AzureRmAccount` cmdlet. You'll also need the service principal's application ID,
sign-in credentials, and the tenant ID associate with the service principal. To get the service principal's credentials as the appropriate object, use the [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential) cmdlet. This cmdlet will display a dialog box to enter the service principal user ID and password into.

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
```

## Sign in using an Azure Managed Service Identity

Managed identities for Azure resources is a feature of Azure Active Directory. You can use a managed identity
service principal for sign-in, and acquire an app-only access token to access other resources. Managed identities are only available on
virtual machines running in an Azure cloud.

For more information about managed identities for Azure resources, see
[How to use managed identities for Azure resources on an Azure VM to acquire an access token](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token).

## Sign in to another Cloud

Azure cloud services offer environments compliant with regional data-handling regulations.
For accounts in a regional cloud, set the environment when you sign in with the `-Environment` argument.
For example, if your account is in the China cloud:

```azurepowershell-interactive
Connect-AzureRmAccount -Environment AzureChinaCloud
```

The following command gets a list of available environments:

```azurepowershell-interactive
Get-AzureRmEnvironment | Select-Object Name
```

## Learn more about managing Azure role-based access

For more information about authentication and subscription management in Azure, see
[Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure).

Azure PowerShell cmdlets for role management:

* [Get-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [Get-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [New-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [New-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [Remove-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [Remove-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [Set-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Set-AzureRmRoleDefinition)
