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
interface, which is useful for ad-hoc management tasks and for environments that require manual
sign-in, such as those with multi-factor authentication (MFA). This method simplifies access for
script testing, learning, and on-the-fly management without needing to pre-configure service
principals or other noninteractive authentication methods.

## Prerequisites

- [Install the latest version of the Az PowerShell module][install-azps].

## Interactive login

Azure PowerShell's default login authentication method uses a web browser and access token to sign
in.

1. To sign in interactively, use the `Connect-AzAccount` cmdlet, which uses an interactive
   browser-based login prompt by default.

   ```azurepowershell
   Connect-AzAccount
   ```

   If Azure PowerShell can open your default browser, it initiates
   [authorization code flow][authorization-code-flow] and opens the default browser to load an Azure
   sign-in page. Otherwise, it initiates [device code flow][device-code-flow] which instructs you to
   open a browser page at [microsoft.com/devicelogin][ms-devicelogin] and enter the code displayed
   in your PowerShell session.

1. Sign in with your Azure account credentials in the browser.

If you have access to multiple subscriptions, you're signed in to the first subscription Azure
returns. Commands run against this subscription by default. To change your active subscription for a
session, use the `Set-AzContext` cmdlet. To change your active subscription and have it persist
between sessions on the same system, use the `Select-AzContext` cmdlet.

> [!IMPORTANT]
> Your credentials are shared among multiple PowerShell sessions as long as you remain signed in.
> For more information, see [Azure PowerShell context objects][context-persistence].

### Device code authentication

If no web browser is available or it fails to open, you can force device code flow instead of a
browser control by specifying the **UseDeviceAuthentication** parameter.

```azurepowershell
Connect-AzAccount -UseDeviceAuthentication
```

### Sign in to a different tenant

If your account is associated with more than one tenant, sign-in requires the **Tenant** parameter
to be specified when connecting. This parameter works with any sign-in method. When logging in, this
parameter value can either be the Azure object ID of the tenant (Tenant ID) or the fully qualified
domain name of the tenant. Due to limitations of the current API, you must use a tenant ID instead
of a tenant name when connecting with a business-to-business (B2B) account.

```azurepowershell
Connect-AzAccount -Tenant '00000000-0000-0000-0000-000000000000'
```

### Sign in to a national cloud

National clouds (also known as sovereign clouds) are physically isolated instances of Azure designed
to ensure data residency, sovereignty, and compliance requirements are honored within geographical
boundaries. For accounts in a national cloud, set the environment when you sign in using the
**Environment** parameter. This parameter works with any sign-in method. For example, if your
account is in Azure China 21Vianet, use the following command:

```azurepowershell
Connect-AzAccount -Environment AzureChinaCloud
```

You can get a list of available environments by running the following command:

```azurepowershell
Get-AzEnvironment | Select-Object -Property Name
```

## Web Account Manager (WAM)

Azure PowerShell now offers preview support for Web Account Manager (WAM). WAM is a Windows 10+
component that acts as an authentication broker. An authentication broker is an application that
runs on a user's machine that manages the authentication handshakes and token maintenance for
connected accounts.

Using WAM offers several benefits:

- Enhanced security. See
  [Conditional Access: Token protection (preview)][token-protection].
- Support for Windows Hello, conditional access policies, and FIDO keys.
- Streamlined single sign-on.
- Bug fixes and enhancements shipped with Windows.

> [!NOTE]
> Signing in using WAM is an opt-in preview feature.

Once enabled, the previous browser-based user interface is replaced with a smoother experience
similar to Windows built-in apps. To enable WAM, run the following commands.

```azurepowershell
Update-AzConfig -EnableLoginByWam $true
Connect-AzAccount
```

At the current stage of development, there are a few known limitations to WAM:

- WAM is available on Windows 10 and later, and on Windows Server 2019 and later. On Mac, Linux, and
  earlier versions of Windows, Azure PowerShell automatically defaults to a browser.
- Microsoft Accounts (for example, @outlook.com or @live.com) aren't currently supported. We're
  working with the Microsoft Identity team to bring the support later.

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
