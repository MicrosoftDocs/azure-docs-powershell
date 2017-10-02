---
title: Persisting user logins across PowerShell sessions
description: The article explains new features in Azure PowerShell that allow you to reuse credentials and other user information across multiple PowerShell sessions.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/31/2017
---
# Persisting user logins across PowerShell sessions

In the September 2017 release of Azure PowerShell, Azure Resource Manager cmdlets introduce a new
feature, **Azure Context Autosave**. This feature enables several new user scenarios,
including:

- Retention of login information for reuse in new PowerShell sessions.
- Easier use of background tasks for executing long-running cmdlets.
- Switch between accounts, subscriptions, and environments without a separate login.
- Execution of tasks using different credentials and subscriptions, simultaneously, from the same
  PowerShell session.

## Azure contexts defined

An *Azure context* is a set of information that defines the target of Azure PowerShell cmdlets. The
context consists of five parts:

- An *Account* - the UserName or Service Principal used to authenticate communications with Azure
- A *Subscription* - The Azure Subscription containing the Resources being acted upon.
- A *Tenant* - The Azure Active Directory tenant that contains your subscription. Tenants are more
  important to ServicePrincipal authentication.
- An *Environment* - The particular Azure Cloud being targeted, usually the Azure global Cloud.
  However, the environment setting allows you to target National, Government, and on-premises
  (Azure Stack) clouds as well.
- *Credentials* - The information used by Azure to verify your identity and ensure your
  authorization to access resources in Azure

In previous releases, your Azure Context had to be created each time you opened a new PowerShell
session. Beginning with Azure PowerShell v4.4.0, you can enable the automatic saving and reuse of
Azure Contexts whenever you open a new PowerShell session.

## Automatically saving the context for the next login

By default, Azure PowerShell discards your context information whenever you close the
PowerShell session.

To allow Azure PowerShell to remember your context after the PowerShell session is closed, use
`Enable-AzureRmContextAutosave`. Context and credential information are automatically saved in
a special hidden folder in your user directory (`%AppData%\Roaming\Windows Azure PowerShell`).
Subsequently, each new PowerShell session targets the context used in your last session.

To set PowerShell to forget your context and credentials, use `Disable-AzureRmContextAutoSave`. You
will need to log in to Azure every time you open a PowerShell session.

The cmdlets that allow you to manage Azure contexts also allow you fine grained control. If you
want changes to apply only to the current PowerShell session (`Process` scope) or every PowerShell
session (`CurrentUser` scope). These options are discussed in mode detail in [Using Context
Scopes](#Using-Context-Scopes).

## Running Azure PowerShell cmdlets as background jobs

The **Azure Context Autosave** feature also allows you to share you context with PowerShell
background jobs. PowerShell allows you to start and monitor long-executing tasks as background jobs
without having to wait for the tasks to complete. You can share credentials with background jobs in
two different ways:

- Passing the context as an argument

  Most AzureRM cmdlets allow you to pass the context as a parameter to the cmdlet. You can pass a
  context to a background job as shown in the following example:

  ```powershell
  PS C:\> $job = Start-Job { param ($ctx) New-AzureRmVm -AzureRmContext $ctx [... Additional parameters ...]} -ArgumentList (Get-AzureRmContext)
  ```

- Using the default context with Autosave enabled

  If you have enabled **Context Autosave**, background jobs automatically use the default saved
  context.

  ```powershell
  PS C:\> $job = Start-Job { New-AzureRmVm [... Additional parameters ...]}
  ```

When you need to know the outcome of the background task, use `Get-Job` to check the job status and
`Wait-Job` to wait for the Job to complete. Use `Receive-Job` to capture or display the output of
the background job. For more information, see [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

## Creating, selecting, renaming, and removing contexts

To create a context, you must be logged in to Azure. The `Add-AzureRmAccount` cmdlet (or its alias,
`Login-AzureRmAccount`) sets the default context used by subsequent Azure PowerShell cmdlets, and
allows you to access any tenants or subscriptions allowed by your login credentials.

To add a new context after login, use `Set-AzureRmContext` (or its alias,
`Select-AzureRmSubscription`).

```powershell
PS C:\> Set-AzureRMContext -Subscription "Contoso Subscription 1" -Name "Contoso1"
```

The previous example adds a new context targeting 'Contoso Subscription 1' using your current
credentials. The new context is named 'Contoso1'. If you do not provide a name for the context, a
default name, using the account ID and subscription ID is used.

To rename an existing context, use the `Rename-AzureRmContext` cmdlet. For example:

```powershell
PS C:\> Rename-AzureRmContext '[user1@contoso.org; 123456-7890-1234-564321]` 'Contoso2'
```

This example renames the context with automatic name `[user1@contoso.org; 123456-7890-1234-564321]`
to the simple name 'Contoso2'. Cmdlets that manage contexts also use tab completion, allowing you
to quickly select the context.

Finally, to remove a context, use the `Remove-AzureRmContext` cmdlet.  For example:

```powershell
PS C:\> Remove-AzureRmContext Contoso2
```

Forgets the context that was named 'Contoso2'. You can recreate this context subsequently using
`Set-AzureRmContext`

## Removing credentials

You can remove all credentials and associated contexts for a user or service principal using
`Remove-AzureRmAccount` (also known as `Logout-AzureRmAccount`). When executed without parameters,
the `Remove-AzureRmAccount` cmdlet removes all credentials and contexts associated with the User or
Service Principal in the current context. You may pass in a Username, Service Principal Name, or
context to target a particular principal.

```powershell
Remove-AzureRmAccount user1@contoso.org
```

## Using context scopes

Occasionally, you may want to select, change, or remove a context in a PowerShell session without
impacting other sessions. To change the default behavior of context cmdlets, use the `Scope`
parameter. The `Process` scope overrides the default behavior by making it apply only for the
current session. Conversely `CurrentUser` scope changes the context in all sessions, instead of
just the current session.

As an example, to change the default context in the current PowerShell session without impacting
other windows, or the context used the next time a session is opened, use:

```powershell
PS C:\> Select-AzureRmContext Contoso1 -Scope Process
```

## How the context autosave setting is remembered

The context AutoSave setting is saved to the user Azure PowerShell directory
(`%AppData%\Roaming\Windows Azure PowerShell`). Some kinds of computer accounts may not have access
to this directory. For such scenarios, you can use the environment variable

```powershell
$env:AzureRmContextAutoSave="true" | "false"
```

If set to 'true', the context is automatically saved. If set to 'false', the context is not saved.

## Changes to the AzureRM.Profile module

New cmdlets for managing context

- [Enable-AzureRmContextAutosave][enable] - Allow saving the context between powershell sessions.
  Any changes alter the global context.
- [Disable-AzureRmContextAutosave][disable] - Turn off autosaving the context. Each new PowerShell
  session is required to log in again.
- [Select-AzureRmContext][select] - Select a context as the default. All subsequent cmdlets use the
  credentials in this context for authentication.
- [Remove-AzureRmAccount][remove-cred] - Remove all credentials and contexts associated with an
  account.
- [Remove-AzureRmContext][remove-context] - Remove a named context.
- [Rename-AzureRmContext][rename] - Rename an existing context.

Changes to existing profile cmdlets

- [Add-AzureRmAccount][login] - Allow scoping of the login to the process or the current user.
  Allow naming the default context after login.
- [Import-AzureRmContext][import] - Allow scoping of the login to the process or the current user.
- [Set-AzureRmContext][set-context] - Allow selection of existing named contexts, and scope changes
  to the process or current user.

<!-- Hyperlinks -->
[enable]: /powershell/module/azurerm.profile/Enable-AzureRmContextAutosave
[disable]: /powershell/module/azurerm.profile/Disable-AzureRmContextAutosave
[select]: /powershell/module/azurerm.profile/Select-AzureRmContext
[remove-cred]: /powershell/module/azurerm.profile/Remove-AzureRmAccount
[remove-context]: /powershell/module/azurerm.profile/Remove-AzureRmContext
[rename]: /powershell/module/azurerm.profile/Rename-AzureRmContext

<!-- Updated cmdlets -->
[login]: /powershell/module/azurerm.profile/Add-AzureRmAccount
[import]: /powershell/module/azurerm.profile/Import-AzureRmAccount
[set-context]: /powershell/module/azurerm.profile/Import-AzureRmContext
