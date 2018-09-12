---
title: Sign in with Azure PowerShell
description: How to sign in with Azure PowerShell as a user, service principal, or with managed identities for Azure resources.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
---
# Sign in with Azure PowerShell

Azure PowerShell supports multiple authentication methods. The simplest way to get started is to sign in
interactively at the command line.

## Sign in interactively

To sign in interactively, use the [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount) cmdlet.

```azurepowershell
Connect-AzureRmAccount
```

When run, this cmdlet will bring up a dialog box prompting you for your email address and password associated with your Azure account. When you authenticate, that information is saved for the current PowerShell session, the dialog is closed, and you have access to all of the Azure PowerShell cmdlets.

> [!IMPORTANT]
> This sign in is for the current PowerShell session _only_. To persist authentication across multiple
> sessions, see the article on [Persistent Credentials](context-persistence.md).

## Sign in with a service principal

Service principals provide a way for you to create non-interactive accounts that you can use to
manipulate resources. Service principals are like user accounts to which you can apply rules using
Azure Active Directory. By granting the minimum permissions needed to a service principal, you can
ensure your automation scripts are even more secure.

If you need to create a service principal for use with Azure PowerShell, see [Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md).

To sign in with a service principal, use the `-ServicePrincipal` argument with the `Connect-AzureRmAccount` cmdlet. You will also need the service princpal's application ID,
sign-in credentials, and the tenant ID associate with the service principal. In order to get the service principal's credentials as the appropriate object, use the [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential) cmdlet. This cmdlet will display a dialog box to enter the service principal user ID and password into.

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
```

## Sign in using managed identities for Azure resources

Managed identities for Azure resources is a feature of Azure Active Directory. You can use a managed identity
service principal for sign-in, and acquire an app-only access token to access other resources. Managed identities are only available on
virtual machines running in an Azure cloud.

For more information about managed identities for Azure resources, see
[How to use managed identities for Azure resources on an Azure VM to acquire an access token](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token).

## Sign in to another Cloud

Azure cloud services provide different environments that adhere to the data-handling regulations of
various regions. If your Azure account is in a cloud associated with one of these regions, you need to specify the
environment when you sign in. For example, if you account is in the China cloud you sign on using
the following command:

```azurepowershell-interactive
Connect-AzureRmAccount -Environment AzureChinaCloud
```

Use the following command to get a list of available environments:

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
* [Set-AzureRmRoleDefinition](/powershell/moduel/AzureRM.Resources/Set-AzureRmRoleDefinition)
