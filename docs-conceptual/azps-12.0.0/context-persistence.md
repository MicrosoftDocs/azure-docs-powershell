---
description: Learn how to reuse Azure credentials and other information across multiple PowerShell sessions.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure contexts and sign-in credentials
---

# Azure PowerShell context objects

Azure PowerShell uses _Azure PowerShell context objects_ (Azure contexts) to hold subscription and
authentication information. If you have access to multiple subscriptions, Azure contexts let you
select the subscription to run Azure PowerShell cmdlets on. Azure contexts are also used to store
sign-in information across multiple PowerShell sessions and run background tasks.

This article covers managing Azure contexts, not the management of subscriptions or accounts. If you
want to manage users, subscriptions, tenants, or other account information, see the
[Microsoft Entra ID][entra-docs] documentation. To learn about using contexts for running background
or parallel tasks, see [Run Azure PowerShell cmdlets in PowerShell Jobs][using-psjobs] after
becoming familiar with Azure contexts.

## Overview of Azure context objects

Azure contexts are PowerShell objects representing your active subscription to run commands against
and the authentication information needed to connect to an Azure cloud. With Azure contexts, Azure
PowerShell doesn't need to reauthenticate your account each time you switch subscriptions. An Azure
context consists of:

- The _account_ that was used to sign in to Azure with `Connect-AzAccount`. Azure contexts treat
  users, application IDs, and service principals the same from an account perspective.
- The active _subscription_, a service agreement with Microsoft to create and run Azure resources,
  which are associated with a _tenant_. Tenants are often referred to as _organizations_ in
  documentation or when working with Microsoft Entra.
- A reference to a _token cache_, a stored authentication token for accessing an Azure cloud. The
  [context autosave settings][context-autosave-settings] determine where the token is stored and
  how long it persists.

For more information on these terms, see [Microsoft Entra Terminology][entra-terminology].
Authentication tokens used by Azure contexts are the same as other stored tokens that are part of a
persistent session.

When you sign in with `Connect-AzAccount`, at least one Azure context is created for your default
subscription. The object returned by `Connect-AzAccount` is the default Azure context used for the
rest of the PowerShell session.

## Get Azure contexts

Available Azure contexts are retrieved with the `Get-AzContext` cmdlet. List the available contexts
with the **ListAvailable** parameter:

```azurepowershell-interactive
Get-AzContext -ListAvailable
```

Or get a context by name:

```azurepowershell-interactive
Get-AzContext -Name MyContextName
```

Context names may be different from the name of the associated subscription. To determine the
context name, use the value of the **Name** property, which isn't displayed by default.

```azurepowershell-interactive
Get-AzContext -ListAvailable | Select-Object -Property *
```

> [!IMPORTANT]
> The available Azure contexts aren't always your available subscriptions. Azure contexts only
> represent locally stored information. You can get your subscriptions with the `Get-AzSubscription`
> cmdlet.

## Create a new Azure context from subscription information

The `Set-AzContext` cmdlet is used to create and set new Azure contexts as the active context. The
easiest way to create a new Azure context is to use existing subscription information. The
`Set-AzContext` cmdlet is designed to take the output object from `Get-AzSubscription` as a piped
value and configure a new Azure context:

```azurepowershell-interactive
Get-AzSubscription -SubscriptionName MySubscriptionName |
  Set-AzContext -Name MyContextName
```

Or give the subscription name or ID and the tenant ID if necessary:

```azurepowershell-interactive
Set-AzContext -Name MyContextName -Subscription MySubscriptionName -Tenant 00000000-0000-0000-0000-000000000000
```

If the **Name** parameter is omitted, then the subscription's name and ID are used as the context
name in the format `Subscription Name (subscription-id)`.

## Change the active Azure context

Both `Set-AzContext` and `Select-AzContext` can be used to change the active Azure context. As
described in [Create a new Azure context][create-new-context], `Set-AzContext` creates a new Azure
context for a subscription if one doesn't exist and then switches the active context to that one.

`Select-AzContext` is meant to be used only with existing Azure contexts and works similarly to
using `Set-AzContext -Context`, but is designed for use with piping:

```azurepowershell-interactive
Set-AzContext -Context (Get-AzContext -Name MyContextName) # Set a context with an inline Azure context object
Get-AzContext -Name MyContextName | Select-AzContext # Set a context with a piped Azure context object
```

Like many other account and context management commands in Azure PowerShell, `Set-AzContext` and
`Select-AzContext` support the **Scope** parameter so that you can control how long the context is
active. **Scope** lets you change a single session's active context without changing your default:

```azurepowershell-interactive
Get-AzContext -Name MyContextName | Select-AzContext -Scope Process
```

To avoid switching contexts for an entire PowerShell session, Azure PowerShell commands with an
**AzContext** parameter can be run against a given context:

```azurepowershell-interactive
$context = Get-AzContext -Name MyContextName
New-AzVM -Name ExampleVM -AzContext $context
```

The other primary use of contexts with Azure PowerShell cmdlets is to run background commands. To
learn more about running PowerShell Jobs using Azure PowerShell, see
[Run Azure PowerShell cmdlets in PowerShell Jobs][using-psjobs].

## Save Azure contexts across PowerShell sessions

By default, Azure contexts are saved for use between PowerShell sessions. You can change this
behavior in the following ways:

- Sign in using `-Scope Process` with `Connect-AzAccount`.

  ```azurepowershell
  Connect-AzAccount -Scope Process
  ```

  The Azure context returned as part of this sign-in is valid for the current session _only_ and
  aren't saved automatically, regardless of the Azure PowerShell context autosave setting.
- Disable context autosave in Azure PowerShell with the `Disable-AzContextAutosave` cmdlet.
  Disabling context autosave doesn't clear any stored tokens. To learn how to clear stored Azure
  context information, see
  [Remove Azure contexts and stored credentials][remove-contexts-and-credentials].
- Explicitly enable Azure context autosave can be enabled with the `Enable-AzContextAutosave`
  cmdlet. With autosave enabled, a user's contexts are stored locally for later PowerShell sessions.
- Manually save contexts with `Save-AzContext` to be used in future PowerShell sessions, where they
  can be loaded with `Import-AzContext`:

  ```azurepowershell
  Save-AzContext -Path current-context.json # Save the current context
  Import-AzContext -Path other-context.json # Load the context from a file and set it to the current context
  ```

> [!WARNING]
> Disabling context autosave doesn't clear any stored context information that was saved. To remove
> stored information, use the `Clear-AzContext` cmdlet. For more on removing saved contexts, see
> [Remove Azure contexts and stored credentials][remove-contexts-and-credentials].

Each of these commands supports the **Scope** parameter, which can take a value of `Process` to only
apply to the current running process. For example, to ensure that newly created contexts aren't
saved after exiting a PowerShell session:

```azurepowershell-interactive
Disable-AzContextAutosave -Scope Process
Set-AzContext -Subscription 'Subscription ID or Name' -Tenant 00000000-0000-0000-0000-000000000000
```

Context information and tokens are stored in the `$env:USERPROFILE\.Azure` directory on Windows and
`$HOME/.Azure` on other platforms. Sensitive information such as subscription IDs and tenant IDs may
still be exposed in stored information, through logs, or saved contexts. To learn how to clear
stored information, see
[Remove Azure contexts and stored credentials][remove-contexts-and-credentials].

## Remove Azure contexts and stored credentials

To clear Azure contexts and credentials:

- Sign out of an account with `Disconnect-AzAccount`. You can sign out of any account either by
  account or context:

  ```azurepowershell-interactive
  Disconnect-AzAccount # Disconnect active account
  Disconnect-AzAccount -Username 'user@contoso.com' # Disconnect by account name
  Disconnect-AzAccount -ContextName MyContextName # Disconnect by context name

  $context = Get-AzContext
  Disconnect-AzAccount -AzureContext $context # Disconnect using context object information
  ```

  Disconnecting always removes stored authentication tokens and clears saved contexts associated
  with the disconnected user or context.
- Use `Clear-AzContext`. This cmdlet always removes stored contexts and authentication tokens and
  signs you out.
- Remove a context with `Remove-AzContext`:

  ```azurepowershell-interactive
  Remove-AzContext -Name MyContextName # Remove by name
  Get-AzContext -Name MyContextName | Remove-AzContext # Remove by piping an Azure context object
  ```

  If you remove the active context, you're disconnected from Azure and need to reauthenticate with
  `Connect-AzAccount`.

## See also

- [Connect-AzAccount][connect-azaccount]
- [Disconnect-AzAccount][disconnect-azaccount]
- [Get-AzContext][get-azcontext]
- [Set-AzContext][set-azcontext]
- [Save-AzContext][save-azcontext]
- [Select-AzContext][select-azcontext]
- [Import-AzContext][import-azcontext]
- [Clear-AzContext][clear-azcontext]
- [Remove-AzContext][remove-azcontext]
- [Enable-AzContextAutosave][enable-azcontextautosave]
- [Disable-AzContextAutosave][disable-azcontextautosave]
- [Get-AzSubscription][get-azsubscription]

<!-- link references -->

[entra-docs]: /azure/active-directory
[using-psjobs]: using-psjobs.md
[context-autosave-settings]: #save-azure-contexts-across-powershell-sessions
[entra-terminology]: /azure/active-directory/fundamentals/active-directory-whatis#terminology
[remove-contexts-and-credentials]: #remove-azure-contexts-and-stored-credentials
[connect-azaccount]: /powershell/module/az.accounts/connect-azaccount
[disconnect-azaccount]: /powershell/module/az.accounts/disconnect-azaccount
[get-azcontext]: /powershell/module/az.accounts/get-azcontext
[set-azcontext]: /powershell/module/Az.Accounts/Set-AzContext
[select-azcontext]: /powershell/module/az.accounts/set-azcontext
[save-azcontext]: /powershell/module/az.accounts/save-azcontext
[import-azcontext]: /powershell/module/az.accounts/import-azcontext
[remove-azcontext]: /powershell/module/az.accounts/remove-azcontext
[create-new-context]: #create-a-new-azure-context-from-subscription-information
[clear-azcontext]: /powershell/module/az.accounts/Clear-AzContext
[enable-azcontextautosave]: /powershell/module/az.accounts/enable-azcontextautosave
[disable-azcontextautosave]: /powershell/module/az.accounts/disable-azcontextautosave
[get-azsubscription]: /powershell/module/Az.Accounts/Get-AzSubscription
