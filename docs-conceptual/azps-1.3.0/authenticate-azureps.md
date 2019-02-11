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

Azure PowerShell supports several authentication methods. The easiest way to get started is with [Azure Cloud Shell](/azure/cloud-shell/overview), which automatically logs you in. With a local install, you can sign in interactively through your browser. When writing scripts for automation, the recommended approach is to use a [service principal](create-azure-service-principal-azureps.md) with the necessary permissions. When you restrict sign-in permissions as much as possible for your use case, you help keep your Azure resources secure.

After signing in, commands are run against your default subscription. To change your active subscription for a session, use the [Set-AzContext](/powershell/module/az.accounts/set-azcontext) cmdlet. To change the default subscription used when logging in with Azure PowerShell, use [Set-AzDefault](/powershell/module/az.accounts/set-azdefault).

> [!IMPORTANT]
>
> Your credentials are shared among multiple PowerShell sessions as long as you remain signed in.
> For more information, see the article on [Persistent Credentials](context-persistence.md).

## Sign in interactively

To sign in interactively, use the [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount) cmdlet.

```azurepowershell-interactive
Connect-AzAccount
```

When run, this cmdlet will present a token string. To sign in, copy this string and paste it into https://microsoft.com/devicelogin in a browser. Your PowerShell session will
be authenticated to connect to Azure.

## Sign in with credentials

You can also sign in with a `PSCredential` object authorized to connect to Azure.
The easiest way to get a credential object is with the [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential) cmdlet. When run, this cmdlet will prompt you for a username/password credential pair.

> [!Note]
> This approach doesn't work with Microsoft accounts or accounts that have two-factor authentication enabled.

```azurepowershell-interactive
$creds = Get-Credential
Connect-AzAccount -Credential $creds
```

## Sign in with a service principal

Service principals are non-interactive Azure accounts. Like other user accounts, their permissions are managed with Azure Active Directory. By granting a service principal only the permissions it needs, your automation scripts stay secure.

To learn how to create a service principal for use with Azure PowerShell, see [Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md).

To sign in with a service principal, use the `-ServicePrincipal` argument with the `Connect-AzAccount` cmdlet. You'll also need the service principal's application ID,
sign-in credentials, and the tenant ID associate with the service principal. To get the service principal's credentials as the appropriate object, use the [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential) cmdlet. This cmdlet will present a prompt for the service principal user ID and password.

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
```

## Sign in using a managed identity 

Managed identities are a feature of Azure Active Directory. Managed identities are service principals assigned to resources that run in Azure. You can use a managed identity
service principal for sign-in, and acquire an app-only access token to access other resources. Managed identities are only available on resources running in an Azure cloud.

To learn more about managed identities for Azure resources, see
[How to use managed identities for Azure resources on an Azure VM to acquire an access token](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token).

## Sign in with a non-default tenant or as a Cloud Solution Provider (CSP)

If your account is associated with more than one tenant, sign-in requires the use of the `-TenantId` parameter
when connecting. This parameter will work with any other sign-in method. When logging in, this parameter value
can either be the Azure object ID of the tenant (Tenant ID) or the fully qualified domain name of the tenant.

If you're a [Cloud Solution Provider (CSP)](https://azure.microsoft.com/en-us/offers/ms-azr-0145p/), the `-TenantId` value **must** be a tenant ID.

```azurepowershell-interactive
Connect-AzAccount -TenantId 'xxxx-xxxx-xxxx-xxxx'
```

## Sign in to another Cloud

Azure cloud services offer environments compliant with regional data-handling laws.
For accounts in a regional cloud, set the environment when you sign in with the `-Environment` argument.
For example, if your account is in the China cloud:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

The following command gets a list of available environments:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object Name
```