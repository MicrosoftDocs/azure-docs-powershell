---
title: Introducing the Azure Az PowerShell module
description: Introducing the Az PowerShell module, recommended for interacting with Azure, and the replacement for the AzureRM PowerShell module.
ms.date: 02/12/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Introducing the Azure Az PowerShell module

## Overview

The Az PowerShell module is a set of cmdlets for managing Azure resources directly from PowerShell. PowerShell
provides powerful features for automation that can be leveraged for managing your Azure resources
for examples in the context of a CI/CD pipeline.

The Az PowerShell module is the replacement of AzureRM and is the recommended version to use for
interacting with Azure.

You can use the Az PowerShell module with one of the following methods:

* [Install the Az PowerShell module via PowerShellGet](install-az-ps.md) (recommended option).
* [Install the Az PowerShell module with MSI](install-az-ps-msi.md).
* [Use Azure Cloud Shell](/azure/cloud-shell/overview).
* [Use the Az PowerShell Docker container](azureps-in-docker.md).

## Features

The Az PowerShell module features the following benefits:

* Security and stability
  * Token cache encryption
  * Prevention of man-in-the-middle attack type
  * Support authentication with ADFS 2019
  * Username and password authentication in PowerShell 7
  * Support for features like continuous access evaluation (coming in 2021)
* Support for all Azure services
  * All generally available Azure services have a corresponding supported PowerShell module
  * Multiple bug fixes and API version upgrades since AzureRM
* New capabilities
  * Support in Cloud Shell and cross-platform
  * Can get and use access token to access Azure resources
  * Cmdlet available for advanced REST operations with Azure resources

> [!NOTE]
> PowerShell 7 and later is the recommended version of PowerShell for use with Az PowerShell on
> all platforms.

The Az PowerShell module is based on the .NET Standard library and works with PowerShell 7 and later
on all platforms including Windows, macOS, and Linux. It's also compatible with Windows PowerShell
5.1.

We're committed to bringing Azure support to all platforms and all Az PowerShell modules are cross-platforms.

## Upgrade your environment to Az

To keep up with the latest Azure features in PowerShell, you should migrate to the Az module. If
you're not ready to install the Az module as a replacement for AzureRM, you have a couple of options
available to experiment with Az:

* Use a `PowerShell` environment with [Azure Cloud Shell](/azure/cloud-shell/overview). Azure Cloud
  Shell is a browser-based shell environment that comes with the Az module installed and
  `Enable-AzureRM` compatibility aliases enabled.
* Keep the AzureRM module installed in Windows PowerShell 5.1 and install the Az module in
  PowerShell 7 or later. Windows PowerShell 5.1 and PowerShell 7 and later use separate
  collections of modules. Follow the instructions to install the
  [latest version of PowerShell](/powershell/scripting/install/installing-powershell) and then
  [install the Az module](install-az-ps.md) from PowerShell 7 or later.

To upgrade from an existing AzureRM install:

1. [Uninstall the Azure PowerShell AzureRM module](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
1. [Install the Azure PowerShell Az module](install-az-ps.md)
1. **OPTIONAL**: Enable compatibility mode to add aliases for AzureRM cmdlets with
   [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) while you become
   familiar with the new command set. For more information, see the next section or
   [Start migration from AzureRM to Az](migrate-from-azurerm-to-az.md).

## Migrate existing scripts from AzureRM to Az

If your scripts are still based on the AzureRM module, we have several resources to help you with
the migration:

* [Get started with migration from AzureRM to Az](migrate-from-azurerm-to-az.md)
* [Full list of breaking changes from AzureRM to Az 1.0.0](migrate-az-1.0.0.md)
* The [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) cmdlet

## Supportability

Az is the most current PowerShell module for Azure. Issues or feature requests can be logged
directly on the [GitHub repository](https://github.com/Azure/azure-powershell), or via Microsoft
support if you have a support contract. Feature requests will be implemented in the latest version
of Az. Critical issues will be implemented on the last two versions of Az.

Because Az PowerShell modules now have all the capabilities of AzureRM PowerShell modules and more,
we'll retire AzureRM PowerShell modules on 29 February 2024.

To avoid service interruptions, [update your scripts](https://aka.ms/azpsmigrate) that use AzureRM
PowerShell modules to use Az PowerShell modules by 29 February 2024. To automatically update your
scripts, follow the [quickstart guide](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## Data collection

Azure PowerShell collects telemetry data by default. Microsoft aggregates collected data to identify
patterns of usage to identify common issues and to improve the experience of Azure PowerShell.
Microsoft Azure PowerShell does not collect any private or personal data. For example, the usage
data helps identify issues such as cmdlets with low success and helps prioritize our work.

While we appreciate the insights this data provides, we also understand that not everyone wants to
send usage data. You can disable data collection with the
[`Disable-AzDataCollection`](/powershell/module/az.accounts/disable-azdatacollection) cmdlet. You
can also read our [privacy statement](https://privacy.microsoft.com/privacystatement) to learn more.
