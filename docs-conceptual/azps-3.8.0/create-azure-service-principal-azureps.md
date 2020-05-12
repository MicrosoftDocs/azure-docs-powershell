---
title: Use Azure service principals with Azure PowerShell
description: Learn how to create and use service principals with Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 04/23/2019
---
# Create an Azure service principal with Azure PowerShell

Automated tools that use Azure services should always have restricted permissions. Instead of having
applications sign in as a fully privileged user, Azure offers service principals.

An Azure service principal is an identity created for use with
applications, hosted services, and automated tools to access
Azure resources. This access is restricted by the roles assigned
to the service principal, giving you control over which resources
can be accessed and at which level. For security reasons, it's
always recommended to use service principals with automated
tools rather than allowing them to log in with a user identity.

This article shows you the steps for creating, getting information about, and resetting a service principal with Azure PowerShell.

## Create a service principal

Create a service principal with the [New-AzADServicePrincipal](/powershell/module/Az.Resources/New-AzADServicePrincipal) cmdlet. When creating a service principal, you choose the type of sign-in authentication it uses.

> [!NOTE]
>
> If your account doesn't have permission to create a service principal, `New-AzADServicePrincipal` will return an error message containing
> "Insufficient privileges to complete the operation." Contact your Azure Active Directory admin to create a service principal.

There are two types of authentication available for service principals: Password-based authentication, and certificate-based authentication.

### Password-based authentication

Without any other authentication parameters, password-based authentication is used and a random password created for you. If you want password-based authentication, this method is recommended.

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

The returned object contains the `Secret` member, which is a `SecureString` containing the generated password. Make sure that you store this value somewhere secure to authenticate with the service principal. Its value __won't__ be displayed in the console output. If you lose the password, [reset the service principal credentials](#reset-credentials).

The following code will allow you to export the secret:

```azurepowershell-interactive
$BSTR = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($sp.Secret)
$UnsecureSecret = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($BSTR)
```

For user-supplied passwords, the `-PasswordCredential` argument takes `Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential` objects. These objects must have a valid `StartDate` and `EndDate`, and take a plaintext `Password`. When creating a password, make sure you follow the [Azure Active Directory password rules and restrictions](/azure/active-directory/active-directory-passwords-policy). Don't use a weak password or reuse a password.

```azurepowershell-interactive
Import-Module Az.Resources # Imports the PSADPasswordCredential object
$credentials = New-Object Microsoft.Azure.Commands.ActiveDirectory.PSADPasswordCredential -Property @{ StartDate=Get-Date; EndDate=Get-Date -Year 2024; Password=<Choose a strong password>}
$sp = New-AzAdServicePrincipal -DisplayName ServicePrincipalName -PasswordCredential $credentials
```

The object returned from `New-AzADServicePrincipal` contains the `Id` and `DisplayName` members, either of which can be used for sign in with the service principal.

> [!IMPORTANT]
>
> Signing in with a service principal requires the tenant ID which the service principal was created under. To get the active tenant when the service principal was created, run the following command __immediately after__ service principal creation:
>
> ```azurepowershell-interactive
> (Get-AzContext).Tenant.Id
> ```

### Certificate-based authentication

Service principals using certificate-based authentication are created with the `-CertValue` parameter. This parameter takes a base64-encoded ASCII string of the public certificate. This is represented by a PEM file,
or a text-encoded CRT or CER. Binary encodings of the public certificate aren't supported. These instructions assume that you already
have a certificate available.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -CertValue $cert
```

You can also use the `-KeyCredential` parameter, which takes `PSADKeyCredential` objects. These objects must have a valid `StartDate`, `EndDate`, and have the `CertValue` member set to a base64-encoded ASCII string of the public certificate.

```azurepowershell-interactive
$cert = <public certificate as base64-encoded string>
$credentials = New-Object Microsoft.Azure.Commands.ActiveDirectory.PSADKeyCredential -Property @{ StartDate=Get-Date; EndDate=Get-Date -Year 2024; KeyId=New-Guid; CertValue=$cert}
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName -KeyCredential $credentials
```

The object returned from `New-AzADServicePrincipal` contains the `Id` and `DisplayName` members, either of which can be used for sign in with the service principal. Clients which sign in with the service principal also need access to the certificate's private key.

> [!IMPORTANT]
>
> Signing in with a service principal requires the tenant ID which the service principal was created under. To get the active tenant when the service principal was created, run the following command __immediately after__ service principal creation:
>
> ```azurepowershell-interactive
> (Get-AzContext).Tenant.Id
> ```

## Get an existing service principal

A list of service principals for the currently active tenant can be retrieved with [Get-AzADServicePrincipal](/powershell/module/az.resources/get-azadserviceprincipal). By default this command returns __all__ service principals in a tenant, so for large organizations, it may take a long time to return results. Instead, using one of the optional server-side filtering arguments is recommended:

* `-DisplayNameBeginsWith` requests service principals that have a _prefix_ that match the provided value. The display name of a service principal is the value set with `-DisplayName` during creation.
* `-DisplayName` requests an _exact match_ of a service principal name.

## Manage service principal roles

Azure PowerShell has the following cmdlets to manage role assignments:

* [Get-AzRoleAssignment](/powershell/module/az.resources/get-azroleassignment)
* [New-AzRoleAssignment](/powershell/module/az.resources/new-azroleassignment)
* [Remove-AzRoleAssignment](/powershell/module/az.resources/remove-azroleassignment)

The default role for a service principal is **Contributor**. This role has full permissions to read and write to an Azure account. The **Reader** role is more restrictive, with read-only access.  For more information on Role-Based Access Control (RBAC) and roles, see [RBAC: Built-in roles](/azure/active-directory/role-based-access-built-in-roles).

This example adds the **Reader** role and removes the **Contributor** one:

```azurepowershell-interactive
New-AzRoleAssignment -ApplicationId <service principal application ID> -RoleDefinitionName "Reader"
Remove-AzRoleAssignment -ApplicationId <service principal application ID> -RoleDefinitionName "Contributor"
```

> [!IMPORTANT]
> Role assignment cmdlets don't take the service principal object ID. They take the associated application ID, which is generated at creation time. To get the application ID for a service principal, use `Get-AzADServicePrincipal`.

> [!NOTE]
> If your account doesn't have permission to assign a role, you see an error message that your account "does not have authorization to
> perform action 'Microsoft.Authorization/roleAssignments/write'." Contact your Azure Active Directory admin to manage roles.

Adding a role _doesn't_ restrict previously assigned permissions. When restricting a service principal's permissions, the __Contributor__ role should be removed.

The changes can be verified by listing the assigned roles:

```azurepowershell-interactive
Get-AzRoleAssignment -ServicePrincipalName ServicePrincipalName
```

## Sign in using a service principal

Test the new service principal's credentials and permissions by signing in. To sign in with a service principal, you need the `applicationId` value associated with it, and the tenant it was created under.

To sign in with a service principal using a password:

```azurepowershell-interactive
# Use the application ID as the username, and the secret as password
$credentials = Get-Credential
Connect-AzAccount -ServicePrincipal -Credential $credentials -Tenant <tenant ID> 
```

Certificate-based authentication requires that Azure PowerShell can retrieve information from a local certificate
store based on a certificate thumbprint.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -Tenant <tenant ID> -CertificateThumbprint <thumbprint>
```

For instructions on importing a certificate into a credential store accessible by PowerShell, see [Sign in with Azure PowerShell](authenticate-azureps.md#sp-signin)

## Reset credentials

If you forget the credentials for a service principal, use [New-AzADSpCredential](/powershell/module/az.resources/new-azadspcredential) to add a new credential. This cmdlet takes the same credential arguments and types as `New-AzADServicePrincipal`. Without any credential arguments, a new `PasswordCredential` with a random password is created.

> [!IMPORTANT]
> Before assigning any new credentials, you may want to remove existing credentials to prevent sign in with them. To do so, use the [Remove-AzADSpCredential](/powershell/module/az.resources/remove-azadspcredential) cmdlet:
>
> ```azurepowershell-interactive
> Remove-AzADSpCredential -DisplayName ServicePrincipalName
> ```

```azurepowershell-interactive
$newCredential = New-AzADSpCredential -ServicePrincipalName ServicePrincipalName
```
