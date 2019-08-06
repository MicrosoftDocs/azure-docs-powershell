---
title: Credential contexts in Azure PowerShell
description: Learn how to reuse Azure credentials and other information across multiple PowerShell sessions.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/05/2019
---
# Azure PowerShell contexts and cross-session credentials

Azure PowerShell uses _Azure context_ objects to hold some sign-in information and authentication tokens. Context objects are used to run cmdlets against specific
subscriptions and switch between accounts. Contexts are also used to store sign in information across multiple PowerShell sessions, and run background tasks.

This article covers context management and selecting contexts to use in a PowerShell session or with individual cmdlets.
To learn about using contexts for running background or parallel tasks, see [Use Azure PowerShell cmdlets in PowerShell jobs](using-psjobs.md).

## Accounts, subscriptions, and contexts

Contexts and subscriptions are tightly bound together. Azure contexts are local representations of a subscription, so that Azure PowerShell doesn't need to
communicate with the cloud when you switch subscriptions associated with a single account. In detail:

* Your _account_ is used to sign in to Azure with [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount). In Azure PowerShell contexts,
  an account is either a user, an application ID, or a service principal.
* _Subscriptions_ are collections of Azure resources associated with a _tenant_. An account can belong to multiple tenants, and each tenant can have
  multiple subscriptions. Tenant administrators manage which accounts have access to which subscriptions. Tenants are also often referred to as "Organizations."
* _Azure contexts_ are objects representing a subscription sign-in. Contexts contain a an account, subscription, and tenant to identify a
  user. Context objects also have an authentication token for connecting to Azure. Contexts don't store any passwords.

For more details on accounts, subscriptions, and tenants, see [Azure Active Directory Terminology](/azure/active-directory/fundamentals/active-directory-whatis#terminology).
Authentication tokens used by Azure contexts are the same as other stored tokens that are part of a persistent session.

## Create contexts and get information

Contexts for each of your subscriptions are created automatically when you sign in to Azure with `Connect-AzAccount`. This is the only way contexts can be created -
they are managed entirely by the sign-in process and Azure PowerShell. The return value of `Connect-AzAccount` is the default context used for the rest of the
PowerShell session. One context is created for every subscription available to the signed in account.

Contexts are inspected with the [Get-AzContext](...) cmdlet. All of the available contexts can be listed with `-ListAvailable`, or a specific context can be
inspected with the `-Name` argument:

```azurepowershell-interactive
Get-AzContext -ListAvailable
```

A specific context can be inspected with `-Name`:

```azurepowershell-interactive
$context = Get-Context -Name "subscription 1"
```

## Change the active context

You change a PowerShell session's active context with [Set-AzContext](/powershell/module/az.accounts/set-azcontext).
This cmdlet can take a context name, context object, or a tenant and subscription pair:

```azurepowershell-interactive
Set-AzContext -Name "subscription 1" # By name
Get-AzContext -Name "subscription 1" | Set-AzContext # With context as input object
Set-AzContext -Tenant "TenantID_or_name" -Subscription "SubID_or_name" # By tenant/subscription pair
```

Like many other account and context management commands in Azure PowerShell, `Select-AzContext` also supports the `-Scope` argument
so that you can control how long the context is active. This lets you change a single session's active context without changing the
default:

```azurepowershell-interactive
Set-AzContext -Name "subscription 1" -Scope Process
```

To avoid switching contexts for a whole PowerShell session, all Azure PowerShell commands can be run against a given
context with the `-AzContext` argument:

```azurepowershell-interactive
$context = Get-AzContext -Name "subscription 1"
New-AzVM -Name ExampleVM -AzContext $context
```

The other main use of contexts with Azure PowerShell cmdlets is to run background commands. To learn more about running
PowerShell Jobs using Azure PowerShell, see [Run Azure PowerShell cmdlets in PowerShell Jobs](using-psjobs.md).

## Save contexts across PowerShell sessions

By default, Azure PowerShell contexts are saved for use between PowerShell sessions. To manage how contexts are saved:

* Sign in using `-Scope Process` with `Connect-AzAccount`.
  Contexts for this account are valid for the current session _only_ and will not be saved, regardless of
  the Azure PowerShell context autosave setting.
* Sign out using `-Scope Process` with `Disconnect-AzAccount`.  
* Disable context autosave with the [Disable-AzContextAutosave](/powershell/module/az.accounts/disable-azcontextautosave) cmdlet.
  Disabling context autosave __doesn't__ clear any stored tokens.
* Context autosave can be enabled with the [Enable-AzContextAutosave](/powershell/module/az.accounts/enable-azcontextautosave)
  cmdlet. With autosave enabled, all of a user's contexts are stored locally for later PowerShell sessions.
* Manually save contexts with [Save-AzContext](/powershell/module/az.accounts/save-azcontext) to be used in future PowerShell sessions.

> [!WARNING]
> Disabling context autosave __doesn't__ clear any stored context information that was saved. To remove stored information, use the
> [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext) cmdlet. For more on removing saved contexts, see
> [Remove contexts and credentials](#remove-contexts-and-credentials)

Each of these commands supports the `-Scope` parameter, which can take a value of `Process` to only apply
to the current running process. For example, to ensure that newly created contexts aren't saved after exiting a PowerShell session:

```azurepowershell-interactive
Disable-AzContextAutosave -Scope Process
$context2 = Set-AzContext -Subscription "sub-id" -Tenant "other-tenant"
```

Context information and tokens are stored in the `$env:USERPROFILE\.Azure` directory on Windows, and on `$HOME/.Azure`
on other platforms. Sensitive information such as subscription IDs and tenant IDs may still be exposed in
this directory, through logs or unencrypted session information. To learn how to clear stored
information, see the
[Remove contexts and credentials](#remove-contexts-and-credentials) section.

## Remove contexts and credentials

To clear stored contexts and credentials:

* Sign out of an account with [Disconnect-AzAccount](/powershell/module/az.accounts/disconnect-azaccount).
  You can sign out of any account either by account or context:

  ```azurecli-interactive
  Disconnect-AzAccount # Disconnect active account 
  Disconnect-AzAccount -Username "user@contoso.com" # Disconnect by account name

  Disconnect-AzAccount -ContextName "subscription2" # Disconnect by context name
  Disconnect-AzAccount -AzureContext $contextObject # Disconnect using context object information
  ```

  Disconnecting always removes stored authentication tokens, and clears saved contexts if context autosave is enabled.
* Use the [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext) cmdlet. This cmdlet is guaranteed to
  always remove stored contexts and authentication tokens, and will also sign you out.
* Remove a context by name with [Remove-AzContext](/powershell/module/az.accounts/remove-azcontext). Note that this context may be
  recreated the next time you sign in.

## See also

* [Run Azure PowerShell cmdlets in PowerShell Jobs](using-psjobs.md)
* [Azure Active Directory Terminology](/azure/active-directory/fundamentals/active-directory-whatis#terminology)
* [Az.Accounts reference](/powershell/module/az.accounts)