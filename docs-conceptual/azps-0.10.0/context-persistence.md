---
title: Azure contexts and sign-in credentials
description: Learn how to reuse Azure credentials and other information across multiple PowerShell sessions.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/21/2019
---
# Azure PowerShell context objects

Azure PowerShell uses _Azure PowerShell context objects_ (Azure contexts) to hold subscription and authentication information. If you have more than one subscription, Azure contexts let you select the subscription to run Azure PowerShell cmdlets on. Azure contexts are also used to store sign-in information across multiple PowerShell sessions and run background tasks.

This article covers managing Azure contexts, not the management of subscriptions or accounts. If you're looking to manage users, subscriptions, tenants, or other account information, see the [Azure Active Directory](/azure/active-directory) documentation. To learn about using contexts for running background or parallel tasks, see [Use Azure PowerShell cmdlets in PowerShell jobs](using-psjobs.md) after becoming familiar with Azure contexts.

## Overview of Azure context objects

Azure contexts are PowerShell objects representing your active subscription to run commands against, and the authentication information needed to connect to an Azure cloud. With Azure contexts, Azure PowerShell doesn't need to reauthenticate your account each time you switch subscriptions. An Azure context consists of:

* The _account_ that was used to sign in to Azure with [Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount). Azure contexts treat users, application IDs, and service principals the same from an account perspective.
* The active _subscription_, a service agreement with Microsoft to create and run Azure resources, which are associated with a _tenant_. Tenants are often referred to as _organizations_ in documentation or when working with Active Directory.
* A reference to a _token cache_, a stored authentication token for accessing an Azure cloud. Where this token is stored and how long it persists for is determined by the [context autosave settings](#save-azure-contexts-across-powershell-sessions).

For more information on these terms, see [Azure Active Directory Terminology](/azure/active-directory/fundamentals/active-directory-whatis#terminology). Authentication tokens used by Azure contexts are the same as other stored tokens that are part of a persistent session. 

When you sign in with `Connect-AzAccount`, at least one Azure context is created for your default subscription. The object returned by `Connect-AzAccount` is the default Azure context used for the rest of the PowerShell session.

## Get Azure contexts

Available Azure contexts are retrieved with the [Get-AzContext](/powershell/module/az.accounts/get-azcontext) cmdlet. List all of the available contexts with `-ListAvailable`:

```azurepowershell-interactive
Get-AzContext -ListAvailable
```

Or get a context by name:

```azurepowershell-interactive
$context = Get-AzContext -Name "mycontext"
```

Context names may be different from the name of the associated subscription.

> [!IMPORTANT]
> The available Azure contexts __aren't__ always your available subscriptions. Azure contexts only
> represent locally-stored information. You can get your subscriptions
> with the [Get-AzSubscription](/powershell/module/Az.Accounts/Get-AzSubscription?view=azps-1.8.0) cmdlet.

## Create a new Azure context from subscription information

The [Set-AzContext](/powershell/module/Az.Accounts/Set-AzContext) cmdlet is used to both create new Azure contexts and set them as the active context.
The easiest way to create a new Azure context is to use existing subscription information. The cmdlet is designed to take the output object from `Get-AzSubscription` as
a piped value and configure a new Azure context:

```azurepowershell-interactive
Get-AzSubscription -SubscriptionName 'MySubscriptionName' | Set-AzContext -Name 'MyContextName'
```

Or give the subscription name or ID and the tenant ID if necessary:

```azurepowershell-interactive
Set-AzContext -Name 'MyContextName' -Subscription 'MySubscriptionName' -Tenant '.......'
```

If the `-Name` argument is omitted, then the subscription's name and ID are used as the context name in the format `Subscription Name (subscription-id)`.

## Change the active Azure context

Both `Set-AzContext` and [Select-AzContext](/powershell/module/az.accounts/set-azcontext) can be used to change the active Azure context. As described in [Create a new Azure context](#create-a-new-azure-context-from-subscription-information), `Set-AzContext` creates a new Azure context for a subscription if one doesn't exist, and then switches to use that context as the active one.

`Select-AzContext` is meant to be used with existing Azure contexts only and works similarly to using `Set-AzContext -Context`, but is designed for use with piping:

```azurepowershell-interactive
Set-AzContext -Context $(Get-AzContext -Name "mycontext") # Set a context with an inline Azure context object
Get-AzContext -Name "mycontext" | Select-AzContext # Set a context with a piped Azure context object
```

Like many other account and context management commands in Azure PowerShell, `Set-AzContext` and `Select-AzContext` support the `-Scope` argument so that you can control how long the context is active. `-Scope` lets you change a single session's active context without changing the default:

```azurepowershell-interactive
Get-AzContext -Name "mycontext" | Select-AzContext -Scope Process
```

To avoid switching contexts for a whole PowerShell session, all Azure PowerShell commands can be run against a given context with the `-AzContext` argument:

```azurepowershell-interactive
$context = Get-AzContext -Name "mycontext"
New-AzVM -Name ExampleVM -AzContext $context
```

The other main use of contexts with Azure PowerShell cmdlets is to run background commands. To learn more about running PowerShell Jobs using Azure PowerShell, see [Run Azure PowerShell cmdlets in PowerShell Jobs](using-psjobs.md).

## Save Azure contexts across PowerShell sessions

By default, Azure contexts are saved for use between PowerShell sessions. You change this behavior in the
following ways:

* Sign in using `-Scope Process` with `Connect-AzAccount`.

  ```azurepowershell
  Connect-AzAccount -Scope Process
  ```

  The Azure context returned as part of this sign in is valid for the current session _only_ and will not
  be automatically saved, regardless of the Azure PowerShell context autosave setting.
* Disable AzurePowershell's context autosave with the [Disable-AzContextAutosave](/powershell/module/az.accounts/disable-azcontextautosave) cmdlet.
  Disabling context autosave __doesn't__ clear any stored tokens. To learn how to clear stored Azure context
  information, see [Remove Azure contexts and credentials](#remove-azure-contexts-and-stored-credentials).
* Explicitly enable Azure context autosave can be enabled with the [Enable-AzContextAutosave](/powershell/module/az.accounts/enable-azcontextautosave)
  cmdlet. With autosave enabled, all of a user's contexts are stored locally for later PowerShell sessions.
* Manually save contexts with [Save-AzContext](/powershell/module/az.accounts/save-azcontext) to be used in future PowerShell sessions, where they can be
  loaded with [Import-AzContext](/powershell/module/az.accounts/import-azcontext):

  ```azurepowershell
  Save-AzContext -Path current-context.json # Save the current context
  Save-AzContext -Profile $profileObject -Path other-context.json # Save a context object
  Import-AzContext -Path other-context.json # Load the context from a file and set it to the current context
  ```

> [!WARNING]
> Disabling context autosave __doesn't__ clear any stored context information that was saved. To remove stored information, use the
> [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext) cmdlet. For more on removing saved contexts, see
> [Remove contexts and credentials](#remove-azure-contexts-and-stored-credentials).

Each of these commands supports the `-Scope` parameter, which can take a value of `Process` to only apply
to the current running process. For example, to ensure that newly created contexts aren't saved after exiting a PowerShell session:

```azurepowershell-interactive
Disable-AzContextAutosave -Scope Process
$context2 = Set-AzContext -Subscription "sub-id" -Tenant "other-tenant"
```

Context information and tokens are stored in the `$env:USERPROFILE\.Azure` directory on Windows, and on `$HOME/.Azure`
on other platforms. Sensitive information such as subscription IDs and tenant IDs may still be exposed in
stored information, through logs or saved contexts. To learn how to clear stored information, see the
[Remove contexts and credentials](#remove-azure-contexts-and-stored-credentials) section.

## Remove Azure contexts and stored credentials

To clear Azure contexts and credentials:

* Sign out of an account with [Disconnect-AzAccount](/powershell/module/az.accounts/disconnect-azaccount).
  You can sign out of any account either by account or context:

  ```azurepowershell-interactive
  Disconnect-AzAccount # Disconnect active account 
  Disconnect-AzAccount -Username "user@contoso.com" # Disconnect by account name

  Disconnect-AzAccount -ContextName "subscription2" # Disconnect by context name
  Disconnect-AzAccount -AzureContext $contextObject # Disconnect using context object information
  ```

  Disconnecting always removes stored authentication tokens and clears saved contexts associated with the
  disconnected user or context.
* Use [Clear-AzContext](/powershell/module/az.accounts/Clear-AzContext). This cmdlet is guaranteed to
  always remove stored contexts and authentication tokens, and will also sign you out.
* Remove a context with [Remove-AzContext](/powershell/module/az.accounts/remove-azcontext):
  
  ```azurepowershell-interactive
  Remove-AzContext -Name "mycontext" # Remove by name
  Get-AzContext -Name "mycontext" | Remove-AzContext # Remove by piping Azure context object
  ```

  If you remove the active context, you will be disconnected from Azure and need to reauthenticate with
  `Connect-AzAccount`.

## See also

* [Run Azure PowerShell cmdlets in PowerShell Jobs](using-psjobs.md)
* [Azure Active Directory Terminology](/azure/active-directory/fundamentals/active-directory-whatis#terminology)
* [Az.Accounts reference](/powershell/module/az.accounts)
