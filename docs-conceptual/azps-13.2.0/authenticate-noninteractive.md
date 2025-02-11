---
description: Learn how to sign in to Azure PowerShell non-interactively using managed identities and service principals for automation scenarios.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Sign in to Azure PowerShell non-interactively for automation scenarios
---

# Sign in to Azure PowerShell non-interactively for automation scenarios

A managed identity in Azure provides a secure and seamless way for applications, services, and
automation tools to access Azure resources without storing credentials in code or configuration.
Unlike service principals, which require manual credential management, Azure automatically handles
managed identities and does not expose sensitive secrets. Using a managed identity is the best
practice for writing secure automation scripts because it simplifies authentication and minimizes
the risk of credential leaks. Managed identities also help automate management tasks securely
without relying on user identities. Permissions for managed identities are managed through Microsoft
Entra, ensuring they have only the necessary access to resources, enhancing both security and
maintainability.

[!INCLUDE [mfa-requirement](../../includes/mfa-requirement.md)]

## Prerequisites

- [Install the latest version of the Az PowerShell module][install-azps].

## Login with a managed identity

Managed identities are a special type of service principal that provide Azure services with an
automatically managed identity. Using this type of identity doesn't require storing credentials in
configuration or code to authenticate to any Azure service that supports managed identities.

There are two types of managed identities:

- System-assigned managed identity
- User-assigned managed identity

Managed identities provide a secure way to communicate with other Azure services without developers
needing to manage credentials. They also help in mitigating the risk of credential leaks.

Here's how managed identities work in real-world scenarios:

- Azure automatically manages the creation and deletion of the credentials used by the managed
  identity.
- An Azure service enabled with a managed identity may securely access other services, such as Azure
  Key Vault, Azure SQL Database, Azure Blob Storage, etc., using Microsoft Entra tokens.
- This identity is managed directly within Azure without needing additional provisioning.

Managed identities simplify the security model by avoiding the need to store and manage credentials,
and they play a crucial role in secure cloud operations by reducing the risk associated with
handling secrets.

### System-assigned managed identity

Azure automatically creates a system-assigned managed identity for an Azure service instance (like
an Azure VM, App Service, or Azure Functions). When the service instance is deleted, Azure
automatically cleans up the credentials and the identity associated with the service.

The following example connects using a system-assigned managed identity of the host environment. If
executed on a virtual machine with an assigned managed identity, it allows the code to sign in using
the assigned identity.

```azurepowershell
 Connect-AzAccount -Identity
```

### User-assigned managed identity

A user-assigned managed identity is an identity you create and manage in Microsoft Entra. It can be
assigned to one or more Azure service instances. The lifecycle of a user-assigned managed identity
is managed separately from the service instances to which it's assigned.

When using a user-assigned managed identity, you must specify the **AccountId** parameter and the
**Identity** parameter, as shown in the following example.

```azurepowershell
 Connect-AzAccount -Identity -AccountId <user-assigned-identity-clientId-or-resourceId>
```

The following commands connect using the managed identity of `myUserAssignedIdentity`. It adds the
user-assigned identity to the virtual machine and then connects using the **ClientId** of the
user-assigned identity.

```azurepowershell
$identity = Get-AzUserAssignedIdentity -ResourceGroupName myResourceGroup -Name myUserAssignedIdentity
Get-AzVM -ResourceGroupName contoso -Name testvm | Update-AzVM -IdentityType UserAssigned -IdentityId $identity.Id
Connect-AzAccount -Identity -AccountId $identity.ClientId # Run on the virtual machine
```

```Output
Account                              SubscriptionName TenantId                             Environment
-------                              ---------------- --------                             -----------
00000000-0000-0000-0000-000000000000 My Subscription  00000000-0000-0000-0000-000000000000 AzureCloud
```

For more information, see
[Configure managed identities for Azure resources on an Azure VM][configure-managed-identity-for-vm].

## Login with a service principal

To sign in with a service principal, use the **ServicePrincipal** parameter of the
`Connect-AzAccount` cmdlet. You'll also need the following information for the service principal:

- AppId
- Sign-in credentials or access to the certificate used to create the service principal
- Tenant ID

How you sign in with a service principal depends on whether it's configured for certificate-based or
password-based authentication.

### Certificate-based authentication

To learn how to create a service principal for Azure PowerShell, see
[Create an Azure service principal with Azure PowerShell][create-service-principal].

Certificate-based authentication requires Azure PowerShell to retrieve information from a local
certificate store based on a certificate thumbprint.

```azurepowershell
Connect-AzAccount -ApplicationId $appId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

When using a service principal instead of a registered application, specify the **ServicePrincipal**
parameter and provide the service principal's AppId as the value for the **ApplicationId**
parameter.

```azurepowershell
Connect-AzAccount -ServicePrincipal -ApplicationId $servicePrincipalId -Tenant $tenantId -CertificateThumbprint <thumbprint>
```

In Windows PowerShell 5.1, the certificate store can be managed and inspected with the
[PKI][pki-module] module. For PowerShell 7.x and later, the process is different. The following
scripts demonstrate how to import an existing certificate into the certificate store that's
accessible by PowerShell.

#### Import a certificate in PowerShell 7.x and later

```powershell
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

#### Import a certificate in Windows PowerShell 5.1

```powershell
# Import a PFX
$credentials = Get-Credential -Message 'Provide PFX private key password'
Import-PfxCertificate -FilePath <path to certificate> -Password $credentials.Password -CertStoreLocation cert:\CurrentUser\My
```

### Password-based authentication

Create a service principal to use with the examples in this section. For more information on
creating service principals, see
[Create an Azure service principal with Azure PowerShell][create-service-principal].

```azurepowershell
$sp = New-AzADServicePrincipal -DisplayName ServicePrincipalName
```

> [!CAUTION]
> The provided service principal secret is stored in the `AzureRmContext.json` file in your user
> profile (`$env:USERPROFILE\.Azure`). Ensure this directory has appropriate protections.

To get the service principal's credentials as an object, use the `Get-Credential` cmdlet. This
cmdlet prompts for a username and password. Use the service principal's `AppId` for the username and
convert its `secret` to plain text for the password.

```azurepowershell
# Retrieve the plain text password for use with Get-Credential in the next command.
$sp.PasswordCredentials.SecretText

$pscredential = Get-Credential -UserName $sp.AppId
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

For automation scenarios, you need to create credentials from a service principal's `AppId` and
`SecretText`:

```azurepowershell
$SecureStringPwd = $sp.PasswordCredentials.SecretText | ConvertTo-SecureString -AsPlainText -Force
$pscredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $sp.AppId, $SecureStringPwd
Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $tenantId
```

Use appropriate password storage practices when automating service principal connections.

## See also

- [Create an Azure service principal with Azure PowerShell][create-service-principal]
- [What are managed identities for Azure resources?][managed-identities-overview]
- [Assign a managed identity access to a resource using PowerShell][assign-managed-identity-access]
- [View the service principal of a managed identity using PowerShell][view-service-principal-of-managed-identity]
- [Connect-AzAccount][connect-azaccount]
- [New-AzADServicePrincipal][new-azadserviceprincipal]
- [Get-Credential][get-credential]

<!-- link references -->

[install-azps]: /powershell/azure/install-azure-powershell
[create-service-principal]: create-azure-service-principal-azureps.md
[get-credential]: /powershell/module/microsoft.powershell.security/get-credential
[pki-module]: /powershell/module/pki
[connect-azaccount]: /powershell/module/az.accounts/connect-azaccount
[new-azadserviceprincipal]: /powershell/module/az.resources/new-azadserviceprincipal
[configure-managed-identity-for-vm]: /entra/identity/managed-identities-azure-resources/qs-configure-powershell-windows-vm
[managed-identities-overview]: /entra/identity/managed-identities-azure-resources/overview
[assign-managed-identity-access]: /entra/identity/managed-identities-azure-resources/how-to-assign-access-azure-resource?pivots=identity-mi-access-powershell
[view-service-principal-of-managed-identity]: /entra/identity/managed-identities-azure-resources/how-to-view-managed-identity-service-principal-powershell
