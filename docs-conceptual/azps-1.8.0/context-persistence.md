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

To create a context, you must be signed in to Azure. The `Connect-AzAccount` cmdlet (or its alias,
`Login-AzAccount`) sets the default context used by Azure PowerShell cmdlets, and
allows you to access any tenants or subscriptions allowed by your credentials.

To add a new context after sign-in, use `Set-AzContext` (or its alias,
`Select-AzSubscription`).

```azurepowershell-interactive
PS C:\> Set-AzContext -Subscription "Contoso Subscription 1" -Name "Contoso1"
```

The previous example adds a new context targeting 'Contoso Subscription 1' using your current
credentials. The new context is named 'Contoso1'. If you don't provide a name for the context, a
default name, using the account ID and subscription ID is used.

To rename an existing context, use the `Rename-AzContext` cmdlet. For example:

```azurepowershell-interactive
PS C:\> Rename-AzContext '[user1@contoso.org; 123456-7890-1234-564321]` 'Contoso2'
```

This example renames the context with automatic name `[user1@contoso.org; 123456-7890-1234-564321]`
to the simple name 'Contoso2'. Cmdlets that manage contexts also use tab completion, allowing you
to quickly select the context.

Finally, to remove a context, use the `Remove-AzContext` cmdlet.  For example:

```azurepowershell-interactive
PS C:\> Remove-AzContext Contoso2
```

Forgets the context that was named 'Contoso2'. You can recreate this context using
`Set-AzContext`

## Removing credentials

You can remove all credentials and associated contexts for a user or service principal using
`Disconnect-AzAccount` (also known as `Logout-AzAccount`). When executed without parameters,
the `Disconnect-AzAccount` cmdlet removes all credentials and contexts associated with the User or
Service Principal in the current context. You may pass in a Username, Service Principal Name, or
context to target a particular principal.

```azurepowershell-interactive
Disconnect-AzAccount user1@contoso.org
```

## Using context scopes

Occasionally, you may want to select, change, or remove a context in a PowerShell session without
impacting other sessions. To change the default behavior of context cmdlets, use the `Scope`
parameter. The `Process` scope overrides the default behavior by making it apply only for the
current session. Conversely `CurrentUser` scope changes the context in all sessions, instead of
just the current session.

As an example, to change the default context in the current PowerShell session without impacting
other windows, or the context used the next time a session is opened, use:

```azurepowershell-interactive
PS C:\> Select-AzContext Contoso1 -Scope Process
```
