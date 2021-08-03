---
title: Sign in with Azure PowerShell
description: How to sign in with Azure PowerShell as a user, service principal, or with managed identities for Azure resources.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/23/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---
# Sign in with Azure PowerShell

Azure PowerShell supports several authentication methods. The easiest way to get started is with
[Azure Cloud Shell](/azure/cloud-shell/overview), which automatically logs you in. With a local
install, you can sign in interactively through your browser. When writing scripts for automation,
the recommended approach is to use a [service principal](create-azure-service-principal-azureps.md)
with the necessary permissions. When you restrict sign-in permissions as much as possible for your
use case, you help keep your Azure resources secure.

Initially, you're signed into the first subscription Azure returns if you have access to more than
one subscription. Commands are run against this subscription by default. To change your active
subscription for a session, use the [Set-AzContext](/powershell/module/az.accounts/set-azcontext)
cmdlet. To change your active subscription and have it persist between sessions on the same system,
use the [Select-AzContext](/powershell/module/az.accounts/select-azcontext) cmdlet.

> [!IMPORTANT]
> Your credentials are shared among multiple PowerShell sessions as long as you remain signed in.
> For more information, see the article on [Persistent Credentials](context-persistence.md).

## Sign in interactively

To sign in interactively, use the
[Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount) cmdlet.

```azurepowershell-interactive
Connect-AzAccount
```

Beginning with Az PowerShell module version 5.0.0, this cmdlet presents an interactive browser based
login prompt by default. You can specify the `UseDeviceAuthentication` parameter to receive a token
string which was previously the default for PowerShell version 6 and higher.

> [!IMPORTANT]
> Username/password credential authorization has been removed in Azure PowerShell due to changes in
> Active Directory authorization implementations and security concerns. If you use credential
> authorization for automation purposes, instead
> [create a service principal](create-azure-service-principal-azureps.md).

Use the [Get-AzContext](/powershell/module/az.accounts/get-azcontext) cmdlet to store your tenant ID
in a variable to be used in the next two sections of this article.

```azurepowershell-interactive
$tenantId = (Get-AzContext).Tenant.Id
```

## Sign in with a service principal <a name="sp-signin"/>

Service principals are non-interactive Azure accounts. Like other user accounts, their permissions
are managed with Azure Active Directory. By granting a service principal only the permissions it
needs, your automation scripts stay secure.

To learn how to create a service principal for use with Azure PowerShell, see
[Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md).

To sign in with a service principal, use the `-ServicePrincipal` argument with the
`Connect-AzAccount` cmdlet. You'll also need the service principal's application ID, sign-in
credentials, and the tenant ID associate with the service principal. How you sign in with a service
principal depends on whether it's configured for password-based or certificate-based
authentication.

### Password-based authentication

Create a service principal to be used in the examples in this section. For more information on
creating service principals, see
[Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps).

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

To get the service principal's credentials as the appropriate object, use the
[Get-Credential](/powershell/module/microsoft.powershell.security/get-credential) cmdlet. This
cmdlet presents a prompt for a username and password. Use the service principal's `applicationID`
for the username and convert its `secret` to plain text for the password.

```azurepowershell-interactive
# Retrieve the plain text password for use with `Get-Credential` in the next command.
$sp.secret | ConvertFrom-SecureString -AsPlainText

$pscredential = Get-Credential -UserName $sp.ApplicationId
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

For automation scenarios, you need to create credentials from a service principal's `applicationId`
and `secret`:

```azurepowershell-interactive
$pscredential = New-Object -TypeName System.Management.Automation.PSCredential($sp.ApplicationId, $sp.Secret)
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Make sure that you use good password storage practices when automating service principal connections.

### Certificate-based authentication

Certificate-based authentication requires that Azure PowerShell can retrieve information from a
local certificate store based on a certificate thumbprint.

```azurepowershell-interactive
Connect-AzAccount -ApplicationId $appId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

When using a service principal instead of a registered application, add the `-ServicePrincipal` argument
and provide the service principal's Application ID as the `-ApplicationId` parameter's value.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -ApplicationId $servicePrincipalId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

In PowerShell 5.1, the certificate store can be managed and inspected with the
[PKI](/powershell/module/pkiclient) module. For PowerShell Core 6.x and later, the process is more
complicated. The following scripts show you how to import an existing certificate into the
certificate store accessible by PowerShell.

#### Import a certificate in PowerShell 5.1

```azurepowershell-interactive
# Import a PFX
$credentials = Get-Credential -Message "Provide PFX private key password"
Import-PfxCertificate -FilePath <path to certificate> -Password $credentials.Password -CertStoreLocation cert:\CurrentUser\My
```

#### Import a certificate in PowerShell Core 6.x and later

```azurepowershell-interactive
# Import a PFX
$storeName = [System.Security.Cryptography.X509Certificates.StoreName]::My
$storeLocation = [System.Security.Cryptography.X509Certificates.StoreLocation]::CurrentUser
$store = [System.Security.Cryptography.X509Certificates.X509Store]::new($storeName, $storeLocation)
$certPath = <path to certificate>
$credentials = Get-Credential -Message "Provide PFX private key password"
$flag = [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::Exportable
$certificate = [System.Security.Cryptography.X509Certificates.X509Certificate2]::new($certPath, $credentials.Password, $flag)
$store.Open([System.Security.Cryptography.X509Certificates.OpenFlags]::ReadWrite)
$store.Add($Certificate)
$store.Close()
```

## Sign in using a managed identity

Managed identities are a feature of Azure Active Directory. Managed identities are service
principals assigned to resources that run in Azure. You can use a managed identity service principal
for sign-in, and acquire an app-only access token to access other resources. Managed identities are
only available on resources running in an Azure cloud.

This example connects using the managed identity of the host environment. For example, if executed
on a VirtualMachine with an assigned Managed Service Identity, this allows the code to sign in using
that assigned identity.

```azurepowershell-interactive
 Connect-AzAccount -Identity
```

## Sign in with a non-default tenant or as a Cloud Solution Provider (CSP)

If your account is associated with more than one tenant, sign-in requires the `-Tenant` parameter to
be specified when connecting. This parameter works with any sign-in method. When logging in, this
parameter value can either be the Azure object ID of the tenant (Tenant ID) or the fully qualified
domain name of the tenant.

If you're a [Cloud Solution Provider (CSP)](https://azure.microsoft.com/offers/ms-azr-0145p/), the
`-Tenant` value **must** be a tenant ID.

```azurepowershell-interactive
Connect-AzAccount -Tenant 'xxxx-xxxx-xxxx-xxxx'
```

## Sign in to another Cloud

Azure cloud services offer environments compliant with regional data-handling laws. For accounts in
a regional cloud, set the environment when you sign in with the `-Environment` argument. This
parameter works with any sign-in method. For example, if your account is in the China cloud:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

The following command gets a list of available environments:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object -Property Name
```
