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
# Azure PowerShell contexts and persisting sessions

Azure PowerShell uses _Azure context_ objects to hold subscription information and authentication tokens. Context objects are used to run cmdlets against specific
subscriptions and switch between accounts. Contexts are also used to store sign in information across multiple PowerShell sessions, and run background tasks.

This article covers context management and selecting contexts to use in a PowerShell session or with individual cmdlets.
To learn about using contexts for running background or parallel tasks, see [Use Azure PowerShell cmdlets in PowerShell jobs](using-psjobs.md).

## Accounts, subscriptions, and contexts

Contexts and subscriptions are tightly bound together. Azure contexts are local representations of a subscription, so that Azure PowerShell doesn't need to
communicate with the cloud when you switch subscriptions associated with a single account. In detail:

* Your _account_ is used to sign in to Azure with [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount). In Azure PowerShell contexts,
  an account is either a user, an application ID, or a service principal.
* _Subscriptions_ are collections of Azure resources associated with a _tenant_. An account can belong to multiple tenants, and each tenant can have
  multiple subscriptions. Tenant administrators manage which accounts have access to which subscriptions.
* _Azure contexts_ are the local representation of a subscription. Contexts are PowerShell objects which reference the associated account, subscription,
  and tenant, then tie those values together with an authorization token. This token is what's used to authenticate commands run on the cloud.

For more details on accounts, subscriptions, and tenants, see [Azure Active Directory Terminology](/azure/active-directory/fundamentals/active-directory-whatis#terminology).

## Create, select, and manage contexts

To create and update contexts, you must be signed in to Azure. Whenever you sign in to Azure with `Connect-AzAccount`, new contexts are created locally for use with Azure PowerShell. Each subscription for an account's default tenant has an associated context created for it.

To get an existing context, use the [Get-AzContext](/powershell/module/az.accounts/Get-AzContext) cmdlet. All of the stored context information is available with the `-ListAvailable` argument. To get a specific context, use the `-Name` parameter. For example, to get the saved context for `subscription 1`:

```azurepowershell-interactive
$context = Get-Context -Name "subscription 1"
```

You change a PowerShell session's active context with the [Select-AzContext](/powershell/module/az.accounts/select-azcontext). This cmdlet can take either a context name or an object:

```azurepowershell-interactive
Select-AzContext -Name "subscription 1" # By name
Get-AzContext -Name "subscription 1" | Select-AzContext # With context as input object
```

To avoid switching contexts for a whole PowerShell session, all Azure PowerShell commands support the `-AzContext`
optional argument:

```azurepowershell-interactive
$context = Get-AzContext -Name "subscription 1"
New-AzVM -Name ExampleVM -AzContext $context
```

You change the currently active context with the [Select-AzContext](/powershell/module/az.accounts/select-azcontext). Like many other account and context management commands in Azure PowerShell, `Select-AzContext` also supports the `-Scope` argument so that you can control how long the context is active. This lets you change a single session's active context without changing the default.

To create a new context, use [Set-AzContext](/powershell/module/Az.Accounts/Set-AzContext). This command automatically sets the created context as the active context. If the new context doesn't exist in the store yet, a new context is automatically created for you and saved if context autosave is enabled.
This context can be named with the `-Name` argument to be easily retrieved later, and requires at least
the `-Subscription` argument. The `-Subscription` value can either be a subscription ID, or the subscription
name.

This example adds a new context targeting the subscription `sub2` for tenant `tenant2`:

```azurepowershell-interactive
Set-AzContext -Subscription "my-subscription-2" -Tenant "tenant2" -Name "subscription2"
```

If you don't provide a value for the `-Name` argument, a default name using the subscription name
and ID is generated. Existing contexts can be renamed with the
[Rename-AzContext](/powershell/module/az.accounts/rename-azcontext) cmdlet.

The other main use of contexts is passing them to PowerShell jobs to run background commands. To learn about using contexts
with PowerShell jobs, see [Run Azure PowerShell cmdlets in PowerShell Jobs](using-psjobs.md).

## Change context autosave behavior

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
* Remove a context by name with [Remove-AzContext](/powershell/module/az.accounts/remove-azcontext).

## See also

* [Run Azure PowerShell cmdlets in PowerShell Jobs](using-psjobs.md)
* [Azure Active Directory Terminology](/azure/active-directory/fundamentals/active-directory-whatis#terminology)
* [Az.Accounts reference](/powershell/module/az.accounts)