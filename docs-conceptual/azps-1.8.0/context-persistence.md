---
title: Credential contexts in Azure PowerShell
description: Learn how to reuse Azure credentials and other information across multiple PowerShell sessions.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/21/19
---
# Azure PowerShell contexts and persisting sessions

Azure PowerShell uses an object called an _Azure Context_ to hold sign in information and persist it
across multiple PowerShell sessions. These objects also make it easier to run Azure PowerShell cmdlets
on multiple Azure accounts, switch quickly between accounts, and run background tasks.

This article covers the details of the information contained within an Azure Context, how contexts
are preserved across multiple PowerShell sessions, managing contexts, and manually saving and specifying
contexts on a per-command run.

To learn about using contexts for running background or parallel tasks, see
[Use Azure PowerShell cmdlets in PowerShell jobs](using-psjobs.md).

## Change context autosave behavior

By default, Azure PowerShell contexts are saved for use between PowerShell sessions. There are a few ways
that this behavior can be modified:

* Sign in using `-Scope Process` with [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount).
  This creates a context that is valid for the current session _only_ and will not be saved, regardless of
  the Azure PowerShell context autosave setting.
* Sign out manually with the [Disconnect-AzAccount](/powershell/module/az.accounts/disconnect-azaccount) cmdlet.
  This removes any stored account information for the current context _immediately_ and signs you out.
* Disable context autosave with the [Disable-AzContextAutosave](/powershell/module/az.accounts/disable-azcontextautosave) cmdlet.
  This will remove stored account information for the current context when the _current_ PowerShell session ends,
  while keeping you signed in.
* Context autosave can be explicitly (re)enabled with the [Enable-AzContextAutosave](/powershell/module/az.accounts/enable-azcontextautosave)
  cmdlet. This will return Azure PowerShell to its default state where account information persists between sessions.

Each of these commands supports the `-Scope` parameter, which can take a value of `Process` to only apply
to the current running process. This is most useful with `Disable-AzContextAutosave` when creating more
than one context as part of a session.

Context information is stored in the `$env:USERPROFILE\.Azure` directory on Windows, and on `$HOME/.azure`
on other platforms. Tokens themselves are stored in a secure binary format, but other sensitive information
such as subscription IDs and tenant IDs may still be exposed in this directory.

> [!NOTE]
> If you are disabling automatic sign in as part of a security policy, consider using more aggressive
> or standard security practices first, such as decreasing authentication token timeout, restricting
> Administrator privilges on the local machine, and using more than one local user account. Even without
> context autosaving, sensitive data may be stored in the directory used by Azure PowerShell.

## Manually manage contexts



## Manage contexts

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

```azurepowershell-interactive
PS C:\> Select-AzContext Contoso1 -Scope Process
```
