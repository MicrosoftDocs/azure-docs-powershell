---
title: Introducing the Azure PowerShell Az module
description: Introducing the new Azure PowerShell module Az, the replacement for the AzureRM module.
ms.date: 02/12/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---
# Introducing the new Azure PowerShell Az module

Starting in December 2018, the Azure PowerShell Az module is in general release and is now the
intended PowerShell module for interacting with Azure. Az offers shorter commands, improved
stability, and cross-platform support. Az also has feature parity with AzureRM, giving you an easy
migration path.

> [!NOTE]
> PowerShell 7.x and later is the recommended version of PowerShell for use with Azure PowerShell on
> all platforms.

With the latest Az module, Azure PowerShell works with PowerShell 6.x and later on all platforms
including Windows, macOS, and Linux. It is also compatible with PowerShell 5.1 on Windows.

Az is a new module, so the version has been reset to 1.0.0.

## Why a new module?

Major updates can be inconvenient, so it's important that we let you know why the decision was made
to introduce a new set of modules, with new cmdlets, for interacting with Azure from PowerShell.

The biggest and most important change is that PowerShell has been a cross-platform product since the
introduction of [PowerShell](/powershell/scripting/overview), based on the .NET Standard library.
We're committed to bringing Azure support to all platforms, which means that the Azure PowerShell
modules needed to be updated to use .NET Standard and be compatible with PowerShell Core. Rather
than taking the existing AzureRM module and introduce complex changes to add this support, the Az
module was created.

Creating a new module also allowed our engineers to make the design and naming of cmdlets and
modules consistent. All modules now start with the `Az.` prefix and cmdlets all use the
_Verb_-`Az`_Noun_ form. Previously, cmdlet names were not only longer, there were also
inconsistencies in cmdlet names.

The number of modules was also reduced: Some modules that worked with the same services have been
rolled together. Management plane and data plane cmdlets are now contained all within single modules
for their services. For those of you who manually manage dependencies and imports, this makes things
much simpler.

By making these important changes that required building a new Azure PowerShell module, the team has
committed to making it easier than ever, and on more platforms than previously possible, to use
Azure with PowerShell cmdlets.

## Upgrade to Az

To keep up with the latest Azure features in PowerShell, you should migrate to the Az module as soon
as possible. If you're not ready to install the Az module as a replacement for AzureRM, you have a
couple of options available to experiment with Az:

- Use a `PowerShell` environment with
  [Azure Cloud Shell](/azure/cloud-shell/overview). Azure Cloud Shell is a
  browser-based shell environment that comes with the Az module installed and `Enable-AzureRM`
  compatibility aliases enabled.
- Keep the AzureRM module installed with PowerShell 5.1 for Windows, but install the Az module for
  PowerShell 6.x or later. PowerShell 5.1 for Windows and PowerShell 6.x and later use separate
  collections of modules. Follow the instructions to install the
  [latest version of PowerShell](/powershell/scripting/install/installing-powershell) and then
  [install the Az module](install-az-ps.md) from PowerShell 6.x or later.

To upgrade from an existing AzureRM install:

1. [Uninstall the Azure PowerShell AzureRM module](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
2. [Install the Azure PowerShell Az module](install-az-ps.md)
3. **OPTIONAL**: Enable compatibility mode to add aliases for AzureRM cmdlets with
   [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) while you become
   familiar with the new command set. See the next section or
   [Start migration from AzureRM to Az](migrate-from-azurerm-to-az.md) for more details.

## Migrate existing scripts to Az

The new cmdlet names have been designed to be easy to learn. Instead of using `AzureRm` or `Azure`
in cmdlet names, use `Az`. For example, the old command `New-AzureRMVm` has become `New-AzVm`.
Migration is more than just becoming familiar with the new cmdlet names, though: There are renamed
modules, parameters, and other important changes.

We have several resources to help you with the process of migration from AzureRM to Az:

- [Get started with migration from AzureRM to Az](migrate-from-azurerm-to-az.md)
- [Full list of breaking changes from AzureRM to Az 1.0.0](migrate-az-1.0.0.md)
- The [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) cmdlet

The Az module has a compatibility mode to help you use existing scripts while you update to the new
syntax. The [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) cmdlet enables
a compatibility mode through aliases, to allow you to use existing scripts with minimal modification
while working towards a full migration to Az. By default, `Enable-AzureRmAlias` only enables
compatibility aliases for the current PowerShell session. Use its `Scope` parameter to persist
compatibility aliases across PowerShell sessions. For more information, see
[the Enable-AzureRmAlias reference documentation](/powershell/module/az.accounts/enable-azurermalias).

> [!IMPORTANT]
> Even though the cmdlet names are aliased, there may still be new (or renamed) parameters or
> changed return values for the Az cmdlets. Don't expect enabling aliases to take care of the
> migration for you! See the [full breaking changes list](migrate-az-1.0.0.md) to find where your
> scripts may require updates.

## Support for AzureRM

Because Az PowerShell modules now have all the capabilities of AzureRM PowerShell modules and more,
we'll retire AzureRM PowerShell modules on 29 February 2024.

To avoid service interruptions, [update your scripts](https://aka.ms/azpsmigrate) that use AzureRM
PowerShell modules to use Az PowerShell modules by 29 February 2024. To automatically update your
scripts, follow the [quickstart guide](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).
