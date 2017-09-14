---
title: Support for credential reuse across PowerShell sessions in Azure PowerShell
description: The article explains new features in Azure PowerShell that allow you to reuse credentials across multiple PowerShell sessions.
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
# Support for credential reuse across PowerShell sessions in Azure PowerShell

With the September 2017 release of Azure PowerShell, the Azure PowerShell Profile cmdlets changed
to support persistence of credentials between sessions. Context information and credentials are
automatically saved to disk when the user enables Autosave. This saved context allows users to use
PowerShell jobs without having to perform separate authentication steps within the job.

## New environment Variable

The `Azure_Profile_Autosave` environment variable controls whether the context is automatically
saved to the default location. Default is 'false'.

```powershell
$env:Azure_Profile_Autosave="true" | "false"
```

Autosave can be managed using the new `Enable-AzureRmContextAutosave` and
`Disable-AzureRmContextAutosave` cmdlets.

## Changes to Add-AzureRmAccount

Allow scoping the login, so it can affect only the process or the current user.

```powershell
Add-AzureRmAccount
```

```powershell
Import-AzureRmContext
```

## Changes to Set-AzureRmContext

Allow changing existing named contexts

```powershell
Set-AzureRmContext -InputObject <IAzureContext> [-Name <string>] [-Subscription(SubscriptionId,
SubscriptionName) <nameOrId>] [-Tenant(TenantId, DomainName) <string>] [-StorageAccount <string>]
[-WhatIf] [-Confirm]

Set-AzureRmContext [-Name <string>] [-Subscription(SubscriptionId, SubscriptionName) <nameOrId>]
[-Tenant(TenantId, DomainName) <string>] [-StorageAccount <string>] [-WhatIf] [-Confirm]
```

## New cmdlet Enable-AzureRmContextAutosave

Allow saving the context between powershell sessions.  Any changes will by default change the global context

```powershell
Enable-AzureRmContextAutosave [-Scope Process | CurrentUser] [-WhatIf] [-Confirm]
```

## New cmdlet Disable-AzureRmContextAutosave

Turn off autosaving the context.  When new powershell windows are opened, each will have to log in.

```powershell
Disable-AzureRmContextAutosave [-Scope Process | CurrentUser] [-WhatIf] [-Confirm]
```

## New cmdlet Select-AzureRmContext

Select a context as the default

```powershell
Select-AzureRmContext -Name <string> [-Scope Process | CurrentUser] [-WhatIf] [-Confirm]
```

## New cmdlet Remove-AzureRmContext

Remove a named context

```powershell
Remove-AzureRmContext [-Name <string>] [-WhatIf] [-Confirm]
```

## New cmdlet Rename-AzureRmContext

Rename an existing context, to make it easire to re-use later

```powershell
Rename-AzureRmContext [-Name <string>] [-WhatIf] [-Confirm]
```

## Changes to default AzureRM cmdlets

```powershell
New-AzureRmWidget [-AzureRmContext(AzureCredentials, AzureRMProfile) <IAzureContextContainer>]
```

## Support for powershell jobs

If context autosave is turned on, you can excute a cmdlet as a job, return immediately, and process
the results later

```powershell
$job = Start-Job {New-AzureRmVM ...}
... cmdlets...
Receive-Job $job
```

## Support for passing the context as a job parameter

Whether or not context autosave is anabled, you can pass in the results of a login, or a context to
a job as a parameter:

```powershell
$job = Start-Job {param ($ctx) New-AzureRmVM -AzureRmContext $ctx ...} -ArgumentList (Get-AzureRmContext "myContextName")
... cmdlets...
Receive-Job $job
```

Profile provider will acquire a read lock when first populating the ContextContainer, and drop it
afterward.

Each cmdlet which changes the context (Add-Account, Import-Context, Set-Context, Select-Context,
Remove-Context) will:

- if operating at the CurrentUser scope, acquire a write lock, read the persisted data, make
  appropariate changes, write the data, and drop the write lock
- if operating at the Process scope, make the changes in memory

TokenCache will operate independently from cmdlets.

- If operating with ContextAutoSaveDisabled scope Cache is saved in the context
- If operating with ContextAutoSaveEnabled, Cache is saved in a file
