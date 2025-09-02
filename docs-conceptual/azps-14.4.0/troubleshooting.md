---
description: Troubleshooting the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
title: Troubleshooting the Az PowerShell module
---

# Troubleshooting the Az PowerShell module

## Enable debug logging

One of the first steps you should take in troubleshooting a problem with the Az PowerShell module is
to enable debug logging.

To enable debug logging on a per command basis, specify the **Debug** parameter.

```azurepowershell-interactive
Get-AzResource -Name 'DoesNotExist' -Debug
```

To enable debug logging for an entire PowerShell session, you set the value of the
**DebugPreference** variable to `Continue`.

```powershell-interactive
$DebugPreference = 'Continue'
```

## Troubleshooting multifactor authentication (MFA)

### Interactive login failures

If you encounter errors when running Azure PowerShell cmdlets that create, modify, or delete
resources, the issue might be caused by a Microsoft Entra ID Conditional Access policy that requires
multifactor authentication (MFA).

These errors typically occur when MFA is required by policy but isn't enforced during login.

#### SharedTokenCacheCredential authentication unavailable

You might see this error when using:

- **Az** PowerShell module version 14.2.0 or earlier
- **Az.Accounts** PowerShell module 5.1.1 or earlier

```Output
SharedTokenCacheCredential authentication unavailable. Token acquisition failed for user
someone@contoso.com. Ensure that you have authenticated with a developer tool that supports Azure
single sign on.
```

Upgrade to the following versions or later to receive more informative error messages and policy
details:

- **Az** PowerShell module: version 14.3.0 or later
- **Az.Accounts** module: version 5.2.0 or later

#### Resource was disallowed by policy

This error occurs in newer module versions (**Az** 14.3.0+ and **Az.Accounts** 5.2.0+), where MFA is
required by Conditional Access for specific operations.

```Output
Resource was disallowed by policy. Users must use MFA for Create operation.
Users must authenticate with multi-factor authentication to create or update resources.
Run the cmdlet below to authenticate interactively; additional parameters may be added as needed.
Connect-AzAccount -Tenant (Get-AzContext).Tenant.Id -ClaimsChallenge "<claims-challenge-token>"
```

#### Resolution options

- Ask your Azure administrator to enforce MFA at sign-in. This allows your session to meet
  Conditional Access requirements without additional steps.
- If MFA enforcement at sign-in isn't possible, use the **ClaimsChallenge** parameter to
  authenticate interactively:

  ```azurepowershell
  Connect-AzAccount -Tenant (Get-AzContext).Tenant.Id -ClaimsChallenge "<claims-challenge-token>"
  ```

For more information, see
[Planning for mandatory multifactor authentication for Azure and other admin portals][01]

### ROPC error: Due to a configuration change made by your administrator

You use the Resource Owner Password Credential (ROPC) flow when signing into Azure using a password.
This authentication method doesn't support MFA. Here's an example:

```azurepowershell
Connect-AzAccount -Credential $Credential
```

If the user account requires MFA, the command fails with the following error:

```Output
Connect-AzAccount : UsernamePasswordCredential authentication failed: Response status code does not
indicate success: 400 (BadRequest). See the troubleshooting guide for more information
https://aka.ms/azsdk/net/identity/usernamepasswordcredential/troubleshoot
```

**Solution:** Use an authentication method that's compatible with MFA.

### Cross-tenant warning: Authentication failed against tenant

If you have access to multiple tenants, and one of them requires MFA, Azure PowerShell might display
the following warning:

```Output
WARNING: Unable to acquire token for tenant '00000000-0000-0000-0000-000000000000' with error
'Authentication failed against tenant 00000000-0000-0000-0000-000000000000. User interaction is
required. This may be due to the conditional access policy settings such as multi-factor
authentication (MFA). If you need to access subscriptions in that tenant, please rerun
'Connect-AzAccount' with additional parameter '-TenantId 00000000-0000-0000-0000-000000000000.'
```

Azure PowerShell attempts to sign in with _the first tenant found_ during login. If that tenant
enforces MFA, authentication might fail. To avoid this issue, explicitly specify the target tenant
using the **TenantId** parameter:

```azurepowershell
Connect-AzAccount -TenantId 00000000-0000-0000-0000-000000000000
```

This ensures that authentication is attempted against the correct tenant, reducing the likelihood of
MFA-related failures.

## Announcement messages in automation scenarios

When connecting to Azure with Azure PowerShell, announcement messages are displayed using
PowerShell's information stream to prevent them from altering the returned object-based output.
Although we've made every effort to ensure the announcement messages don't impact your experience,
there are some automation scenarios where they might affect the usage. If you experience issues, we
recommend that you suppress the information stream in those scenarios:

```azurepowershell
Connect-AzAccount -Subscription '<subscription name or id>' -InformationAction Ignore
```

## Web Account Manager (WAM)

- The interactive sign-in method can't open a window for WAM and returns the error: _User canceled
  authentication_.
- Azure PowerShell cmdlets can't run after logging in with a username and password or device code.
- WAM popup window doesn't display the _Work and School Account_ option.
- The interactive sign-in method can't open a WAM window in the Windows PowerShell ISE console.

The workaround for these issues is to disable WAM:

```azurepowershell
Update-AzConfig -EnableLoginByWam $false
```

- WAM popup window to select an account isn't easy to find. Minimize other windows to locate the
  popup window.

## Installation

This section contains a list of solutions to common problems when installing the Az PowerShell
module.

### Az and AzureRM coexistence

> [!WARNING]
> We do not support having both the AzureRM and Az PowerShell modules installed in Windows
> PowerShell 5.1 at the same time.

In a scenario where you need to install both the AzureRM and Az PowerShell module on the same
Windows system:

- AzureRM must be installed only in the current user scope of Windows PowerShell 5.1.
- Install the Az PowerShell module in PowerShell 7.2 or higher.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

#### Visual Studio

Older versions of Visual Studio may install Azure PowerShell as part of the Azure development
workload, which installs the AzureRM module. Azure PowerShell can be removed using the Visual Studio
installer or by using "Uninstall" in Apps & features. If you have already installed PowerShell 7.x,
you may need to [manually install](install-azure-powershell.md) the Az PowerShell module.

### Proxy blocks connection

If you get errors from `Install-Module` that the PowerShell Gallery is unreachable, you may be
behind a proxy. Different operating systems and network environment have different requirements for
configuring a system-wide proxy. Contact your system administrator for your proxy settings and how
to configure them for your environment.

PowerShell itself may not be configured to use this proxy automatically. With PowerShell 5.1 and
later, configure the PowerShell session to use a proxy using the following commands:

```powershell
$webClient = New-Object -TypeName System.Net.WebClient
$webClient.Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials
```

If your operating system credentials are configured correctly, this configuration routes PowerShell
requests through the proxy. To have this setting persist between sessions, add the commands to your
[PowerShell profile](/powershell/module/microsoft.powershell.core/about/about_profiles).

To install the package, your proxy needs to allow HTTPS connections to [www.powershellgallery.com](https://www.powershellgallery.com).

## Object reference not set to an instance of an object

The message "_object reference not set to an instance of an object_" means that you are referring to
an object that's null or an Azure resource that doesn't exist or that you don't have permissions to
access.

```azurepowershell
$resourceId =  '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/<resource-group-name>/providers/Microsoft.Web/sites/<webapp-name>/privateEndpointConnections/<endpoint-name>'
Get-AzPrivateEndpointConnection -ResourceId $resourceId
```

```Output
Get-AzPrivateEndpointConnection: Object reference not set to an instance of an object.
```

You can use the `Get-AzResource` cmdlet to verify that the specified Azure resource exists.

```azurepowershell
Get-AzResource -ResourceId $resourceId
```

## Permission issues with AzAD cmdlets

The Az PowerShell module uses the Microsoft Graph API. Administering or managing resources in Azure
with the Az PowerShell module requires the same permissions as performing the identical task from
Azure portal or any other Azure command-line tool. For specific questions about permissions see the
[Microsoft Graph permissions reference](/graph/permissions-reference).

## Microsoft Graph query parameters

AzAd cmdlets under Az.Resources now support [query parameters](/graph/query-parameters) and
[search query parameters](/graph/search-query-parameter). For details about the syntax, see the
previously referenced links.

## Get-AzAdGroupMember doesn't return service principals

Due to limitations with the current Graph API, service principals aren't returned by
[Get-AzAdGroupMember](/powershell/module/az.resources/get-azadgroupmember) in Az 7.x. As a
workaround, [Invoke-AzRestMethod](/powershell/module/az.accounts/invoke-azrestmethod) can be used
with the beta version of the Microsoft Graph API.

The following example requires the Az PowerShell module. Replace `myGroupName` in the first line
with the name of your group.

```azurepowershell-interactive
$Group = Get-AzADGroup -DisplayName myGroupName
((Invoke-AzRestMethod -Uri "https://graph.microsoft.com/beta/groups/$($Group.id)/members").Content |
  ConvertFrom-Json).value |
  Select-Object -Property DisplayName, Id, @{label='OdataType';expression={$_.'@odata.type'}}
```

## Command found but could not be loaded

The following message is returned by PowerShell when you attempt to run any of the Az PowerShell commands.

```Output
Connect-AzAccount: The 'Connect-AzAccount' command was found in the module 'Az.Accounts', but the module could not be loaded. For more information, run 'Import-Module Az.Accounts'.
```

This message occurs when you have both the Az and AzureRM PowerShell modules installed on the same
Windows-based system and they exist in the
[$env:PSModulePath](/powershell/module/microsoft.powershell.core/about/about_psmodulepath) for the
same version of PowerShell.

> [!IMPORTANT]
> When AzureRM is installed in the `AllUsers` scope of Windows PowerShell, it's installed in a
> location that's part of the `$env:PSModulePath` for PowerShell 7. This isn't supported due to
> conflicts between the AzureRM and Az PowerShell modules.

Both Az and AzureRM may coexist on the same Windows system, but only if AzureRM is installed in the
`CurrentUser` scope of Windows PowerShell and Az installed in PowerShell 7. For more information,
see [Install the Az PowerShell module](install-azure-powershell.md).

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## On MacOS, an error returns when KeyChain authorization fails

When running Azure PowerShell on MacOS, you might encounter an error message while attempting to
sign in to your Azure account from a PowerShell session.

```txt
DeviceCodeCredential authentication failed: Persistence check failed. Reason: KeyChain authorization/authentication failed. .Error code: -25293. OS error code -25293.
```

As a workaround for this issue, you can disable storing credentials between sessions by running the
following command. After making this change however, you need to run `Connect-AzAccount` each time
you start a new PowerShell session.

```azurepowershell
Disable-AzContextAutosave
```

## The connection for this site is not secure

When your default browser is Microsoft Edge, you might encounter the following error when attempting
to login to Azure interactively with `Connect-AzAccount`: "_The connection for this site is not
secure._" To resolve this issue, visit [edge://net-internals/#hsts](edge://net-internals/#hsts) in
Microsoft Edge. Add `localhost` under "_Delete domain security policy_" and click <kbd>Delete</kbd>.

## Service Principal IdentifierUri verified domain error

Error: _Values of identifierUris property must use a verified domain of the organization or its
subdomain_ is displayed when running `New-AzADServicePrincipal` or `New-AzADApplication`.

Due to the Microsoft Entra breaking change requiring [AppId Uri in single tenant applications
to require use of default scheme or verified
domains](/azure/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains)
you must upgrade the [Az.Resources](https://www.powershellgallery.com/packages/Az.Resources) module
to version 4.1.0 or later to continue using `New-AzADServicePrincipal` or `New-AzADApplication` cmdlets.

You can also upgrade to Az PowerShell module version 6.0 or greater.

### Timeline

The requirement went into effect October 15, 2021.

### Impacted versions

The following versions of Azure PowerShell are affected by the AzureAD breaking change:

- Az.Resources PowerShell module version 3.5.1-preview or lesser.
- Az PowerShell module version 5.9.0 or lesser.

If you are still encountering issues after upgrading, feel free to open an
[issue](https://github.com/Azure/azure-powershell/issues/new?assignees=&labels=needs-triage&template=az-module-bug-report.md&title=).

### Workaround

If you can't upgrade to the PowerShell modules described previously, you may follow those steps when
creating a service principal:

- If needed, [add your custom domain name using Microsoft Entra admin center](/azure/active-directory/fundamentals/add-custom-domain)
- Create an application with an accepted IdentifierUri
- Create a service principal referring this application

## Other issues

If you experience a product issue with Azure PowerShell not listed in this article or require
further assistance, [file an issue on GitHub](https://github.com/azure/azure-powershell/issues).

<!-- link references -->

[01]: /entra/identity/authentication/concept-mandatory-multifactor-authentication
