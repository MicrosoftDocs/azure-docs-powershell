---
title: Migrate Azure PowerShell scripts from AzureRM to Az
description: Learn the steps and tools for migrating Azure PowerShell scripts from AzureRM to the new Az PowerShell module.
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
ms.date: 12/15/2020
ms.custom: devx-track-azurepowershell, contperf-fy21q2
---

# Migrate Azure PowerShell from AzureRM to Az

All versions of the AzureRM PowerShell module are outdated. The [Az PowerShell
module](install-az-ps.md) is now the recommended PowerShell module for interacting with Azure.

## Why a new module?

The biggest and most important change is that [PowerShell](/powershell/scripting/overview), being
based on the .NET Standard library, has been a cross-platform product since its introduction.

Like the PowerShell language, we're committed to bringing Azure support to all platforms. Our
commitment meant that the Azure PowerShell modules needed to be updated to use .NET Standard and be
compatible with PowerShell Core. Rather than modifying the existing AzureRM module and introducing
complex changes to add this support, the Az module was created.

Creating a new module also allowed our engineers to make the design, naming of cmdlets, and modules
consistent. All modules now start with the `Az.` prefix and cmdlets all use the `Verb-AzNoun` naming
convention. Previously, cmdlet names were longer and inconsistent.

The number of modules were also reduced: Some modules that worked with the same services have been
combined. Management plane and data plane cmdlets for the same service are now contained within a
single module. For those of you who manually manage dependencies and imports, this consolidation
makes things much simpler.

By making these important changes, the team has committed to making it easier than ever before and
on more platforms than previously possible to use Azure with PowerShell cmdlets.

## Upgrading to Az PowerShell

Scripts written for the AzureRM cmdlets won't automatically work with Az. To make the
transition easier, the
[AzureRM to Az migration toolkit](https://github.com/Azure/azure-powershell-migration) was
developed. No migration to a new command set is ever convenient, but this article will help you get
started on transitioning to the Az PowerShell module. To learn more about why the Az PowerShell
module was created, see [Introducing the new Azure PowerShell Az module](new-azureps-module-az.md).

The new cmdlet names have been designed to be easy to learn. Instead of using `AzureRm` or `Azure`
in cmdlet names, use `Az`. For example, the old cmdlet `New-AzureRMVm` has become `New-AzVm`.
However, migration is more than just becoming familiar with the new cmdlet names, though. There are
renamed modules, parameters, and other important changes.

To see the full list of breaking changes between AzureRM and Az, see the
[full changes from AzureRM to Az](migrate-az-1.0.0.md).

## Ensure existing scripts work with the latest AzureRM release

Before taking any migration steps, check which versions of AzureRM are installed on your system.
Doing so allows you to make sure scripts are already running on the latest release and let you know
which versions of AzureRM must be uninstalled.

To check which version(s) of AzureRM you have installed, run the following example:

```azurepowershell
Get-Module -Name AzureRM -ListAvailable -All
```

The **latest** available release of AzureRM is **6.13.1**. If you don't have this version installed,
your existing scripts may need additional modifications to work with the Az module beyond the scope
of what's described in this article and in the [breaking changes list](migrate-az-1.0.0.md).

If your scripts don't work with AzureRM 6.13.1, update them according to the
[AzureRM 5.x to 6.x migration guide](/powershell/azure/azurerm/migration-guide.6.0.0). If you use an
earlier version of the AzureRM module, there are migration guides available for each major version.

## Option 1 (recommended): Automatically migrate your PowerShell scripts

This recommended option minimizes the effort required to migrate AzureRM scripts to Az.

### Install the AzureRM to Az migration toolkit

```azurepowershell
Install-Module -Name Az.Tools.Migration
```

### Convert your scripts automatically

With the AzureRM to Az migration toolkit, you can generate a plan to determine what changes will be
performed on your scripts before making any modifications to them and before installing the Az
PowerShell module.

The [Automatically migrate PowerShell scripts from AzureRM to the Az PowerShell module](quickstart-migrate-azurerm-to-az-automatically.md) quickstart walks you through the entire process
of automatically updating your PowerShell scripts from AzureRM to the Az PowerShell module.

## Option 2: Use compatibility mode with Enable-AzureRmAlias

The Az module has a compatibility mode to help you use existing scripts while you update to the new
syntax. The [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) cmdlet enables
a compatibility mode through aliases. This mode allows you to use existing scripts with minimal
modification while working towards a full migration to Az. By default, `Enable-AzureRmAlias` only
enables compatibility aliases for the current PowerShell session. Use its `Scope` parameter to
persist compatibility aliases across PowerShell sessions. For more information, see
[the Enable-AzureRmAlias reference documentation](/powershell/module/az.accounts/enable-azurermalias).

> [!IMPORTANT]
> Even though the cmdlet names are aliased, there may still be new (or renamed) parameters or
> changed return values for the Az cmdlets. Don't expect enabling aliases to take care of the
> migration for you! See the [full breaking changes list](migrate-az-1.0.0.md) to find where your
> scripts may require updates.

## Option 3: Migrate your scripts in Visual Studio Code with the Azure PowerShell extension

### Install the Azure PowerShell extension for Visual Studio Code

Install the [Azure PowerShell extension for VSCode](https://marketplace.visualstudio.com/items?itemName=azps-tools.azps-tools)

### Convert your scripts manually

1. Load your AzureRM script in VSCode
2. Start the migration by opening the command palette `Ctrl+Shift+P` and select `Migrate Azure PowerShell script`
3. Select source version `AzureRM`
4. Follow the recommended actions for each underlined command or parameter.

## Next steps

* [Uninstall AzureRM](uninstall-az-ps.md#uninstall-the-azurerm-module)
* [Install Azure PowerShell](install-az-ps.md)
