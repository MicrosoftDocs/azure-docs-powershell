---
title: Migrate Azure PowerShell scripts from AzureRM to Az
description: Learn the steps and tools for migrating scripts from the AzureRM module to the new Az module.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/01/2018
---

# Migrate from AzureRM to Azure PowerShell Az

The Az module has feature parity with AzureRM, but uses shorter and more consistent cmdlet names.
This means that scripts written for the AzureRM cmdlets won't automatically work with the new
module. To make the transition easier, Az offers tools to allow you to run your existing scripts
using AzureRM. No migration to a new command set is ever convenient, but this article will help
you get started on transitioning to Az while minimizing the cost of upgrading so that you can
take advantage of the features offered in this new module.

Each section of this article outlines a step in the process, and it's recommended that you follow
them in order unless you've already completed the process outlined in a single step.

## Ensure your existing scripts work with the latest AzureRM release

This is the most important step! Run your existing scripts, and make sure that they work with the
_latest_ release of AzureRM (__6.12.0__). If your scripts do not work, make sure to read
the [AzureRM migration guide](migration-guide.6.0.0.md).

## Install the Azure PowerShell Az module

The first step is to install the Az module on your platform. This _does_ require uninstalling
the AzureRM module. In the following steps you'll learn how to keep running your existing scripts
and enable compatibility for old cmdlet names.

To install the Azure PowerShell Az module, follow these steps:

* [Uninstall the AzureRM module](uninstall-azurerm-ps.md). Make sure that you remove _all_ installed versions of AzureRM, not just the most recent version.
* [Install the Az module](install-az-ps.md)

## <a name="aliases"/>Enable AzureRM alias mode

With AzureRM uninstalled and your scripts working with the latest AzureRM version, now is the time to
enable the compatibility mode for the Az module. This is done with the command

```powershell-interactive
Enable-AzureRmAlias -Scope CurrentUser
```

This enables the ability to use old cmdlet names with the `Az` module installed, through aliases. These
aliases are written to the user profile for the selected scope. If no user profile exists, one is created.

> [!WARNING]
>
> You can use a different `-Scope` for this command, but it's not recommended! Aliases are written to
> the user profile for the selected scope, so keep enabling them to as limited a scope as possible. Enabling aliases
> system-wide could also cause issues for other users which have `AzureRM` installed in their local scope.

Once the alias mode is enabled, run your scripts again to confirm that they still function as expected. 

## Change module imports and cmdlet names

In general, the module names have been changed so that `AzureRM` becomes `Az`, and the same for cmdlets.
For example, the `AzureRM.Compute` module has been renamed to `Az.Compute`. `New-AzureRmVM` has become `New-AzVM`.
There are some exceptions to this naming change that you should be aware of before doing any renaming:

| AzureRM module | Az module |
|----------------|-----------|
| Azure.Storage | Az.Storage |
| Azure.AnalysisServices | Az.AnalysisServices |
| AzureRM.DataFactories | Az.DataFactory |
| AzureRM.DataFactoryV2 | Az.DataFactory |
| AzureRM.RecoveryServices.Backup | Az.RecoveryServices |
| AzureRM.RecoveryServices.SiteRecovery | Az.RecoveryServices |

In the case of `Azure.Storage` and `Azure.AnalysisServices`, the associated cmdlets have also been renamed
so that `Azure` is replaced with `Az`. For example, `Get-AzureStorageBlob` has been renamed to `Get-AzStorageBlob`.

## Summary

By following these steps, you can update all of your existing scripts to use the new module without a lot of pain or difficulty.
If you have any questions or encountered problems with these steps that made your migration difficult, please comment on this article
so that we can improve the instructions.