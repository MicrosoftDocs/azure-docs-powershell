---
description: How to sign in with Azure PowerShell as a user, service principal, or with managed identities for Azure resources.
ms.custom: devx-track-azurepowershell
ms.date: 07/18/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Sign in with Azure PowerShell
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
> For more information, see [Azure PowerShell context objects](context-persistence.md).

## Sign in interactively

To sign in interactively, use the
[Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount) cmdlet.

```azurepowershell
Connect-AzAccount
```

This cmdlet presents an interactive browser based login prompt by default.

Use the [Get-AzContext](/powershell/module/az.accounts/get-azcontext) cmdlet to store your tenant ID
in a variable to be used in the next two sections of this article.

```azurepowershell-interactive
$tenantId = (Get-AzContext).Tenant.Id
```

## Device code authentication

You can specify the `UseDeviceAuthentication` parameter to use device code authentication instead of
a browser control.

```azurepowershell-interactive
Connect-AzAccount -UseDeviceAuthentication
```

## Sign in with a service principal

Service principals are non-interactive Azure accounts. Like other user accounts, their permissions
are managed with Azure Active Directory. By granting a service principal only the permissions it
needs, your automation scripts stay secure.

To learn how to create a service principal for use with Azure PowerShell, see
[Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md).

To sign in with a service principal, use the `ServicePrincipal` parameter of the `Connect-AzAccount`
cmdlet. You'll also need the service principal's AppId, sign-in credentials, and the tenant ID
associate with the service principal. How you sign in with a service principal depends on whether
it's configured for password-based or certificate-based authentication.

### Password-based authentication

Create a service principal to be used in the examples in this section. For more information on
creating service principals, see
[Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps).

```azurepowershell-interactive
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

> [!WARNING]
> The provided service principal secret is stored in the `AzureRmContext.json` file in your user
> profile (`$env:USERPROFILE\.Azure`). Ensure this directory has appropriate protections.

To get the service principal's credentials as the appropriate object, use the
[Get-Credential](/powershell/module/microsoft.powershell.security/get-credential) cmdlet. This
cmdlet presents a prompt for a username and password. Use the service principal's `AppId`
for the username and convert its `secret` to plain text for the password.

```azurepowershell-interactive
# Retrieve the plain text password for use with `Get-Credential` in the next command.
$sp.PasswordCredentials.SecretText

$pscredential = Get-Credential -UserName $sp.AppId
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

For automation scenarios, you need to create credentials from a service principal's `AppId` and
`SecretText`:

```azurepowershell-interactive
$SecureStringPwd = $sp.PasswordCredentials.SecretText | ConvertTo-SecureString -AsPlainText -Force
$pscredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $sp.AppId, $SecureStringPwd
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Make sure that you use good password storage practices when automating service principal connections.

### Certificate-based authentication

Certificate-based authentication requires that Azure PowerShell can retrieve information from a
local certificate store based on a certificate thumbprint.

```azurepowershell-interactive
Connect-AzAccount -ApplicationId $appId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

When using a service principal instead of a registered application, specify the **ServicePrincipal**
parameter and provide the service principal's AppId as the value for the **ApplicationId**
parameter.

```azurepowershell-interactive
Connect-AzAccount -ServicePrincipal -ApplicationId $servicePrincipalId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

In Windows PowerShell 5.1, the certificate store can be managed and inspected with the
[PKI](/powershell/module/pki) module. For PowerShell 7.x and later, the process is more complicated.
The following scripts show you how to import an existing certificate into the certificate store
accessible by PowerShell.

#### Import a certificate in Windows PowerShell 5.1

```powershell-interactive
# Import a PFX
$credentials = Get-Credential -Message 'Provide PFX private key password'
Import-PfxCertificate -FilePath <path to certificate> -Password $credentials.Password -CertStoreLocation cert:\CurrentUser\My
```

#### Import a certificate in PowerShell 7.x and later

```powershell-interactive
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
for sign-in, and an app-only access token to access other resources. Managed identities are only
available on resources running in an Azure cloud.

This example connects using a system-assigned managed identity of the host environment. For example,
if executed on a VirtualMachine with an assigned Managed Service Identity, this allows the code to
sign in using that assigned identity.

```azurepowershell-interactive
 Connect-AzAccount -Identity
```

When using a user-assigned managed identity, you must specify the **AccountId** parameter in
addition to the **Identity** parameter as shown in the following example.

```azurepowershell-interactive
 Connect-AzAccount -Identity -AccountId <user-assigned-identity-clientId-or-resourceId>
```

The following example connects using the Managed Service Identity of `myUserAssignedIdentity`. It
adds the user assigned identity to the virtual machine, then connects using the `ClientId` of the
user assigned identity. For more information, see
[Configure managed identities for Azure resources on an Azure VM](/azure/active-directory/managed-identities-azure-resources/qs-configure-powershell-windows-vm).

```azurepowershell-interactive
$identity = Get-AzUserAssignedIdentity -ResourceGroupName 'myResourceGroup' -Name 'myUserAssignedIdentity'
Get-AzVM -ResourceGroupName contoso -Name testvm | Update-AzVM -IdentityType UserAssigned -IdentityId $identity.Id
Connect-AzAccount -Identity -AccountId $identity.ClientId # Run on the virtual machine

Account                SubscriptionName TenantId                Environment
-------                ---------------- --------                -----------
yyyy-yyyy-yyyy-yyyy    Subscription1    xxxx-xxxx-xxxx-xxxx     AzureCloud
```

## Sign in with a non-default tenant or as a Cloud Solution Provider (CSP)

If your account is associated with more than one tenant, sign-in requires the **Tenant** parameter
to be specified when connecting. This parameter works with any sign-in method. When logging in, this
parameter value can either be the Azure object ID of the tenant (Tenant ID) or the fully qualified
domain name of the tenant.

If you're a [Cloud Solution Provider (CSP)](https://azure.microsoft.com/offers/ms-azr-0145p/), the
value for the **Tenant** parameter must be a tenant ID.

```azurepowershell-interactive
Connect-AzAccount -Tenant '00000000-0000-0000-0000-000000000000'
```

## Sign in to another Cloud

Azure cloud services offer environments compliant with regional data-handling laws. For accounts in
a regional cloud, set the environment when you sign in with the **Environment** parameter. This
parameter works with any sign-in method. For example, if your account is in Azure China 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

The following command returns a list of available environments:

```azurepowershell-interactive
Get-AzEnvironment | Select-Object -Property Name
```
