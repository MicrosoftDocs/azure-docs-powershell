---
description: Learn how to sign in to Azure PowerShell as an interactive user for Azure resources using the Connect-AzAccount cmdlet.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Sign in to Azure PowerShell interactively
---

# Sign in to Azure PowerShell interactively

Interactive logins to Azure offer a more intuitive and flexible user experience. Interactive login
with Azure PowerShell allows users to authenticate to Azure directly through the PowerShell
interface, which is helpful for ad-hoc management tasks and environments requiring manual sign-in,
such as those with multifactor authentication (MFA). This method simplifies access for script
testing, learning, and on-the-fly management without needing to preconfigure service principals or
other noninteractive authentication methods.

[!INCLUDE [mfa-requirement](../../includes/mfa-requirement.md)]

## Prerequisites

- [Install the latest version of the Az PowerShell module][install-azps].

## Interactive login

To sign in interactively, use the `Connect-AzAccount` cmdlet. Beginning with Az PowerShell module
version 12.0.0, Windows systems use Web Account Manager (WAM), and Linux and macOS systems use
browser-based login by default.

```azurepowershell
Connect-AzAccount
```

- To learn more about WAM, see [Web Account Manager (WAM)](#web-account-manager-wam)
- To learn more about browser-based login, see [Browser-based login](#browser-based-login)

## Login experience

Beginning with Az PowerShell module version 12.0.0, if you have access to multiple subscriptions,
you're prompted to select an Azure subscription to login with, as shown in the following example.

```Output
Please select the account you want to login with.

Retrieving subscriptions for the selection...
WARNING: To override which subscription Connect-AzAccount selects by default, use
`Update-AzConfig -DefaultSubscriptionForLogin 00000000-0000-0000-0000-000000000000`.
Go to https://go.microsoft.com/fwlink/?linkid=2200610 for more information.
[Tenant and subscription selection]

No    Subscription name                     Subscription ID                           Tenant name
----  ------------------------------------  ----------------------------------------  --------------
[1]   Facility Services Subscription        00000000-0000-0000-0000-000000000000      Contoso
[2]   Finance Department Subscription       00000000-0000-0000-0000-000000000000      Contoso
[3]   Human Resources Subscription          00000000-0000-0000-0000-000000000000      Contoso
[4]   Information Technology Subscription   00000000-0000-0000-0000-000000000000      Contoso

Select a tenant and subscription: 2

Subscription name                       Tenant name
------------------------------------    --------------------------
Finance Department Subscription         Contoso

[Announcements]
With the new Azure PowerShell login experience, you can select the subscription you want to use more easily.
Learn more about it and its configuration at https://go.microsoft.com/fwlink/?linkid=2271236.
Share your feedback regarding your experience with `Connect-AzAccount` at: https://aka.ms/azloginfeedback

If you encounter any problem, please open an issue at: https://aka.ms/azpsissue

Subscription name                      Tenant
-----------------                      ------
Finance Department Subscription        Contoso
```

The next time you login, the previously selected tenant and subscription is marked as the default
with an asterisk (`*`) next to its number and highlighted in a cyan blue color. This allows you to
press <kbd>Enter</kbd> to select the default or type a number to select a different tenant and
subscription.

```Output
No    Subscription name                     Subscription ID                           Tenant name
----  ------------------------------------  ----------------------------------------  --------------
[1]   Facility Services Subscription        00000000-0000-0000-0000-000000000000      Contoso
[2] * Finance Department Subscription       00000000-0000-0000-0000-000000000000      Contoso
[3]   Human Resources Subscription          00000000-0000-0000-0000-000000000000      Contoso
[4]   Information Technology Subscription   00000000-0000-0000-0000-000000000000      Contoso

The default is marked with an *; the default tenant is 'Contoso' and subscription is
'Finance Department Subscription (00000000-0000-0000-0000-000000000000)'.

Select a tenant and subscription (type a number or Enter to accept default): 4

Subscription name                       Tenant name
------------------------------------    --------------------------
Information Technology Subscription     Contoso
```

Commands run against this subscription by default. To change your active subscription, use the
`Set-AzContext` cmdlet. For more information, see
[Azure PowerShell context objects][context-persistence].

### Configure your default subscription for login

To prevent being prompted to select a subscription each time you log in interactively, use the
`Update-AzConfig` cmdlet to set your default subscription, as shown in the following example.

```powershell
Update-AzConfig -DefaultSubscriptionForLogin '<subscription name or id>'
```

### Disable the new login experience

To disable the new login experience, use the `Update-AzConfig` cmdlet, as shown in the following
example.

```powershell
Update-AzConfig -LoginExperienceV2 Off
```

When the new login experience is disabled, and you have access to multiple subscriptions, you're
signed in to the first subscription Azure returns. Commands run against this subscription by
default. To change your active subscription for a session, use the `Set-AzContext` cmdlet. To change
your active subscription and have it persist between sessions on the same system, use the
`Select-AzContext` cmdlet.

## Web Account Manager (WAM)

Beginning with Az PowerShell module version 12.0.0, Azure PowerShell's default login authentication
method for Windows-based systems is Web Account Manager (WAM).

WAM is a Windows 10+ component that acts as an authentication broker. An authentication broker is an
application that runs on your system that manages the authentication handshakes and token
maintenance for connected accounts.

### Benefits of WAM

Using WAM offers several benefits:

- Enhanced security. See
  [Conditional Access: Token protection (preview)][token-protection].
- Support for Windows Hello, conditional access policies, and FIDO keys.
- Streamlined single sign-on.
- Bug fixes and enhancements shipped with Windows.

### Limitations of WAM

At the current stage of development, there are a few known limitations to WAM:

- WAM is available on Windows 10 and later and on Windows Server 2019 and later. On Linux, macOS,
  and earlier versions of Windows, Azure PowerShell automatically defaults to browser-based login.
- Using WAM to log in to national clouds isn't currently supported.
- Microsoft Accounts (for example, @outlook.com or @live.com) must specify the **Tenant** parameter
  when used with MFA.

  ```azurepowershell
  Connect-AzAccount -Tenant 00000000-0000-0000-0000-000000000000
  ```

### Disable WAM

To use browser-based login on Windows 10 and later or on Windows Server 2019 and later with Az
12.0.0 and higher, you must disable WAM for use with Azure PowerShell. Use the following command to
disable WAM and return to browser-based login, the default before Az 12.0.0.

```azurepowershell
Update-AzConfig -EnableLoginByWam $false
```

## Browser-based login

Browser-based login is the default interactive login for Linux, macOS, and Windows systems older
than Windows 10 or Windows Server 2019. Beginning with Az PowerShell module version 12.0.0, you must
[disable WAM](#disable-wam) for Azure PowerShell to use browser-based login on Windows-based
systems, which was the default before Az 12.0.0.

When you sign in interactively with the `Connect-AzAccount` cmdlet, browser-based login opens the
default web browser to load an Azure sign-in page. Sign in with your Azure account credentials in
the browser.

If Azure PowerShell can open your default browser, it initiates
[authorization code flow][authorization-code-flow] and opens the default browser to load an Azure
sign-in page. Otherwise, it initiates [device code flow][device-code-flow], which instructs you to
open a browser page at [microsoft.com/devicelogin][ms-devicelogin] and enter the code displayed in
your PowerShell session.

## Device code authentication

If Web Account Manager or a web browser is unavailable or it fails to open, you can force device
code flow by specifying the **UseDeviceAuthentication** parameter.

```azurepowershell
Connect-AzAccount -UseDeviceAuthentication
```

## Sign in to a different tenant

If your account is associated with more than one tenant, sign-in requires the **Tenant** parameter
to be specified when connecting. This parameter works with any sign-in method. When logging in, this
parameter value can either be the Azure object ID of the tenant (Tenant ID) or the fully qualified
domain name of the tenant.

```azurepowershell
Connect-AzAccount -Tenant 00000000-0000-0000-0000-000000000000
```

## Sign in to a national cloud

National clouds (also known as sovereign clouds) are physically isolated instances of Azure designed
to ensure data residency, sovereignty, and compliance requirements are honored within geographical
boundaries. For accounts in a national cloud, set the environment when you sign in using the
**Environment** parameter. This parameter works with any sign-in method. For example, if your
account is in Azure China 21Vianet, use the following command:

```azurepowershell
Connect-AzAccount -Environment AzureChinaCloud
```

You can get a list of available national cloud environments by running the following command:

```azurepowershell
Get-AzEnvironment | Select-Object -Property Name
```

## See also

- [Connect-AzAccount][connect-azaccount]
- [Set-AzContext][set-azcontext]
- [Select-AzContext][select-azcontext]
- [Update-AzConfig][update-azconfig]

<!-- link references -->

[install-azps]: /powershell/azure/install-azure-powershell
[context-persistence]: context-persistence.md
[authorization-code-flow]: /entra/identity-platform/v2-oauth2-auth-code-flow
[device-code-flow]: /entra/identity-platform/v2-oauth2-device-code
[ms-devicelogin]: https://microsoft.com/devicelogin
[connect-azaccount]: /powershell/module/az.accounts/connect-azaccount
[set-azcontext]: /powershell/module/az.accounts/set-azcontext
[select-azcontext]: /powershell/module/az.accounts/select-azcontext
[token-protection]: /entra/identity/conditional-access/concept-token-protection
[update-azconfig]: /powershell/module/az.accounts/update-azconfig
