---
title: Migrate Azure PowerShell scripts from AzureRM to Az
description: Learn the steps and tools for migrating scripts from the AzureRM module to the new Az module.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 12/13/2018
---

# Migrate from AzureRM to Azure PowerShell Az

The Az module has feature parity with AzureRM, but uses shorter and more consistent cmdlet names.
Scripts written for the AzureRM cmdlets won't automatically work with the new
module. To make the transition easier, Az offers tools to allow you to run your existing scripts
using AzureRM. No migration to a new command set is ever convenient, but this article will help
you get started on transitioning to the new module.

To see the full list of breaking changes between AzureRM and Az, see the [Migration guide for Az 1.0.0](migrate-az-1.0.0.md)

## Check for installed versions of AzureRM

The Az module can be installed side-by-side with the AzureRM module, but this is not recommended. Before
taking any migration steps, check which versions of AzureRM are installed on your system. Doing so
allows you to make sure scripts are already running on the latest release, and let you know
if you can enable command aliases without uninstalling AzureRM.

To check which version(s) of AzureRM you have installed, run the command:

```powershell-interactive
Get-InstalledModule -Name AzureRM -AllVersions
```

## Ensure your existing scripts work with the latest AzureRM release

This is the most important step! Run your existing scripts, and make sure that they work with the
_latest_ release of AzureRM (__6.13.1__). If your scripts don't work, make sure to read
the [AzureRM migration guide](/powershell/azure/azurerm/migration-guide.6.0.0).

## Install the Azure PowerShell Az module

The first step is to install the Az module on your platform. When you install Az, it's recommended
that you uninstall AzureRM. In the following steps, you'll learn how to keep running your existing
scripts and enable compatibility for old cmdlet names.

To install the Azure PowerShell Az module, follow these steps:

* __RECOMMENDED__: [Uninstall the AzureRM module](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module).
  Make sure that you remove _all_ installed versions of AzureRM, not just the most recent version.
* [Install the Az module](install-az-ps.md)

## <a name="aliases"/>Enable AzureRM compatibility aliases 

> [!IMPORTANT]
>
> Only enable compatibility mode if you've uninstalled _all_ versions of AzureRM. Enabling compatibility
> mode with AzureRM cmdlets still available may result in unpredictable behavior. Skip this step if you
> decided to keep AzureRM installed, but be aware that any AzureRM cmdlets will use
> the older modules and not call any Az cmdlets.

With AzureRM uninstalled and your scripts working with the latest AzureRM version, the next step is to 
enable the compatibility mode for the Az module. Compatibility is enabled with the command:

```powershell-interactive
Enable-AzureRmAlias -Scope CurrentUser
```

Aliases enable the ability to use old cmdlet names with the Az module installed. These
aliases are written to the user profile for the selected scope. If no user profile exists, one is created.

> [!WARNING]
>
> You can use a different `-Scope` for this command, but it's not recommended. Aliases are written to
> the user profile for the selected scope, so keep enabling them to as limited a scope as possible. Enabling aliases
> system-wide could also cause issues for other users which have AzureRM installed in their local scope.

Once the alias mode is enabled, run your scripts again to confirm that they still function as expected. 

## Change module imports and cmdlet names

In general, the module names have been changed so that `AzureRM` and `Azure` become `Az`, and the same for cmdlets.
For example, the `AzureRM.Compute` module has been renamed to `Az.Compute`. `New-AzureRMVM` has become `New-AzVM`,
and `Get-AzureStorageBlob` is now `Get-AzStorageBlob`.

There are exceptions to this naming change that you should be aware of. Some modules were renamed or merged into
existing modules without this affecting the suffix of their cmdlets, other than changing `AzureRM` or `Azure`
to `Az`. Otherwise, the full cmdlet suffix was changed to reflect the new module name.

| AzureRM module | Az module | Cmdlet suffix changed? |
|----------------|-----------|------------------------|
| AzureRM.Profile | Az.Accounts | Yes |
| AzureRM.Insights | Az.Monitor | Yes |
| AzureRM.DataFactories | Az.DataFactory | Yes |
| AzureRM.DataFactoryV2 | Az.DataFactory | Yes |
| AzureRM.RecoveryServices.Backup | Az.RecoveryServices | No |
| AzureRM.RecoveryServices.SiteRecovery | Az.RecoveryServices | No |
| AzureRM.Tags | Az.Resources | No |
| AzureRM.MachineLearningCompute | Az.MachineLearning | No |
| AzureRM.UsageAggregates | Az.Billing | No |
| AzureRM.Consumption | Az.Billing | No |

## Summary

By following these steps, you can update all of your existing scripts to use the new module. If you have any questions or problems with these steps that made your migration difficult, please comment on this article so that we can improve the instructions.
