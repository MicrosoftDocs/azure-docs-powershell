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

<!-- TODO: Is this necessary? -->
## Credentials and contexts

The difference between _credentials_ and _contexts_ is subtle but important for working with Azure
PowerShell in advanced scenarios. The most important difference between the two is that _credentials are
used to sign in to Azure_, while _contexts represent a signed in account_. Each context is associated
with exaction one set of credentials, and each set of credentials is associated with one context.

## Change context autosave behavior

By default, Azure PowerShell contexts are saved for use between PowerShell sessions. There are a few ways
that this behavior can be modified:

<!-- TODO: Confirm all of these behaviors -->
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

To create and manage contexts, you must be signed in to Azure. The `Connect-AzAccount` cmdlet sets the
default context used by Azure PowerShell cmdlets, and allows you to access any tenants or subscriptions
allowed by your credentials.

To add a new context after sign-in, use [Set-AzContext](/powershell/module/Az.Accounts/Set-AzContext).
This context can be named with the `-Name` argument to be easily retrieved later, and requires at least
the `-Subscription` argument. The `-Subscription` value can either be a subscription ID, or the subscription
name.

This example adds a new context targeting the subscription `my-subscription-2`, using 
the current context's tenant:

```azurepowershell-interactive
Set-AzContext -Subscription "my-subscription-2" -Name "subscription2"
```

If you don't provide a value for the `-Name` argument, a default name using the subscription name
and ID is generated. Existing contexts can be renamed with the [Rename-AzContext](/powershell/module/az.accounts/rename-azcontext) cmdlet.

To remove a context, use the [Remove-AzContext](/powershell/module/az.accounts/remove-azcontext) cmdlet.
To remove the context created in the last example:

```azurepowershell-interactive
Remove-AzContext -Name "subscription2"
```

<!-- TODO: Is this section needed here? Should content be reorganized? Should make sure that the behavior is correctly described. -->
## Remove contexts and credentials

You can remove all credentials and associated contexts for a user or service principal using
`Disconnect-AzAccount` (also known as `Logout-AzAccount`). When executed without parameters,
the `Disconnect-AzAccount` cmdlet removes all credentials and contexts associated with the User or
Service Principal in the current context. You may pass in a Username, Service Principal Name, or
context to target a particular principal.

```azurepowershell-interactive
Disconnect-AzAccount "login@tenant"
```

## Using context scopes

One of the primary uses of setting up multiple contexts is to change the current active subscription
without needing to sign in or sign out of the active account. There are several ways to change to
another context and run Azure cloud tasks from a different subscription.

* Change the currently active context with [Select-AzContext](/powershell/module/az.accounts/select-azcontext).
  By using the `-Scope` parameter of this command, you can set whether or not this is only valid for
  the current PowerShell session (`Process`) or change to use the selected context as the default for
  this and future sessions (`CurrentUser`).
* Store the context object by using [Get-AzContext](/powershell/module/az.accounts/get-azcontext), and then
  pass it on a per-command basis by using the `-DefaultProfile` (or `-AzContext`) parameter with any Azure
  PowerShell cmdlet. For example, to get the context named "mysubscription" and create a new VM with
  those credentials:
<!-- TODO: Confirm that this is a correct invocation of New-AzVM -->
  ```azurepowershell-interactive
  $context = Get-AzContext -Name "mysubscription"
  New-AzVM -Name "ExampleVM" -DefaultProfile $context 
  ```

The other major use of context scopes is in handling PowerShell jobs. This is described in detail in [Use Azure PowerShell with PowerShell jobs](using-psjobs.md).