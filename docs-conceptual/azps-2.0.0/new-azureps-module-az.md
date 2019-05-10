---
title: Introducing the Azure PowerShell Az module
description: Introducing the new Azure PowerShell module Az, the replacement for the AzureRM module.
ms.date: 12/13/2018
author: sptramer
ms.author: sttramer
ms.manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
---
# Introducing the new Azure PowerShell Az module

Starting in December 2018, the Azure PowerShell Az module is in general release and now the intended
PowerShell module for interacting with Azure. Az offers shorter commands, improved stability, and
cross-platform support. Az also offers feature parity and an easy migration path from AzureRM.

With the Az module, Azure PowerShell is now compatible with PowerShell 5.1 on Windows and PowerShell Core 6.x
and later on all supported platforms - including Windows, macOS, and Linux.

Az is a new module, so the version has been reset to 1.0.0.

## Why a new module?

Major updates can be inconvenient, so it's important that we let you know why the decision was made to
introduce a new set of modules, with new cmdlets, for interacting with Azure from PowerShell.

The biggest and most important change is that PowerShell has been a cross-platform product since the
introduction of [PowerShell Core 6.x](/powershell/scripting/overview), based on the .NET Standard library.
We're committed to bringing Azure support to all platforms, which means that the Azure PowerShell modules
needed to be updated to use .NET Standard and be compatible with PowerShell Core. Rather than taking the
existing AzureRM module and introduce complex changes to add this support, the Az module was created.

Creating a new module also gave our engineers the opportunity to make the design and naming of cmdlets
and modules consistent. All modules now start with the `Az.` prefix and cmdlets all use the
_Verb_-`Az`_Noun_ form. Previously, cmdlet names were not only longer, there were inconsistencies
in cmdlet names.

The number of modules was also reduced: Some modules which worked with the same services have been rolled
together, and magement plane and data plane cmdlets are now contained all within single modules for their
services. For those of you who manually manage dependencies and imports, this makes things much simpler.

By making these important changes that required building a Azure PowerShell module, the team has
committed to making it easier than ever, and on more platforms than previously possible, to use
Azure with PowerShell cmdlets.

## Upgrade to Az

It's recommended that all users upgrade to the new Az module. To do so:

* __RECOMMENDED__: [Uninstall the Azure PowerShell AzureRM module](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
* [Install the Azure PowerShell Az module](/powershell/azure/install-az-ps)
* Enable compatibility mode to add aliases for AzureRM cmdlets with `Enable-AzureRMAlias`
  while you become familiar with the new command set. __Only__ enable aliases if you do not have AzureRM installed.

## Migrate existing scripts to Az

The Az module has a compatibility mode to help you use existing scripts while you work on
updates to the new syntax. Use the [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias)
cmdlet to enable the AzureRM compatibility mode. This cmdlet defines AzureRM cmdlet names as aliases for
the new Az cmdlet names.

> [!IMPORTANT]
> Even though the cmdlet names are aliased, there may still be new (or renamed) parameters for the
> Az cmdlets that will be exposed. Don't expect enabling aliases to take care of the full migration
> for you! After enabling them, test your scripts to make sure they don't need any immediate updates.

The new cmdlet names have been designed to be easy to learn. Instead of using `AzureRm` or `Azure`
in cmdlet names, use `Az`. For example, the old command `New-AzureRMVm` has become `New-AzVm`.

For a full description of the migration process, see [Migrate from AzureRM to Az](migrate-from-azurerm-to-az.md).

## The future of support for AzureRM

The existing AzureRM module will no longer receive new cmdlets or features. However, AzureRM is still officially
maintained and will get bug fixes up through December 2020. To keep up with the latest Azure services and features,
switch to the Az module.
