---
title: Introducing the Azure PowerShell Az module
description: Introducing the new Azure PowerShell module Az, the replacement for the AzureRM module.
ms.date: 11/30/2020
ms.devlang: powershell
ms.topic: conceptual 
ms.custom: devx-track-azurepowershell 
ms.service: azure-powershell
---
# Overview

Az PowerShell is a set of cmdlets for managing Azure resources directly from the Powershell command line.
PowerShell provides powerfull features for automation that can be leveraged for managing your Azure resources for examples in the context of a CI/CD pipeline.

Az PowerShell module is the replacement of AzureRM and is the recommened version to use for interacting with Azure.

You can use Az PowerShell with one of the following methods:

- [Install the Az PowerShell module via PowerShellGet](install-az-ps.md) (recommended option).
- [Install the Az PowerShell module with MSI](install-az-ps-msi.md) (use this option if you do not have internet access when installing).
- [Use Azure CloudShell](/azure/cloud-shell/overview).
- [Use the Az Powershell Docker container](azureps-in-docker.md).

## Features

Az PowerShell features the following benefits:

- Security and stability
  - Token cache encryption
  - Support for ADKS 2019
  - Security mechanism preventing man in the middle attacks types
  - Support for features like continuous access evaluation (coming in 2021)
- Support for all Azure services
  - A module is available for each Azure service
  - Multiple bug fixes and API version upgrade since AzureRM
- Several additional new capabilities
  - Support in CloudShell and cross-platform
  - Can get and use access token to access Azure resources
  - Generic Az cmdlet for escape hatch type operations

> [!NOTE]
> PowerShell 7 and later is the recommended version of PowerShell for use with Az PowerShell on
> all platforms.

Az PowerShell is based on the .NET Standard library, works with PowerShell 7 and later on all platforms including Windows, macOS, and Linux. It is also compatible with PowerShell 5.1 on Windows.

We're committed to bringing Azure support to all platforms and all Az PowerShell modules are cross-platforms.

## Upgrade your environment to Az

To keep up with the latest Azure features in PowerShell, you should migrate to the Az module as soon
as possible. If you're not ready to install the Az module as a replacement for AzureRM, you have a
couple of options available to experiment with Az:

- Use a `PowerShell` environment with
  [Azure Cloud Shell](/azure/cloud-shell/overview). Azure Cloud Shell is a
  browser-based shell environment that comes with the Az module installed and `Enable-AzureRM`
  compatibility aliases enabled.
- Keep the AzureRM module installed with PowerShell 5.1 for Windows, but install the Az module for
  PowerShell 7 or later. PowerShell 5.1 for Windows and PowerShell 7 and later use separate
  collections of modules. Follow the instructions to install the
  [latest version of PowerShell](/powershell/scripting/install/installing-powershell) and then
  [install the Az module](install-az-ps.md) from PowerShell 7 or later.

To upgrade from an existing AzureRM install:

1. [Uninstall the Azure PowerShell AzureRM module](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
2. [Install the Azure PowerShell Az module](install-az-ps.md)
3. **OPTIONAL**: Enable compatibility mode to add aliases for AzureRM cmdlets with
   [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) while you become
   familiar with the new command set. See the next section or
   [Start migration from AzureRM to Az](migrate-from-azurerm-to-az.md) for more details.

## Migrate existing scripts from AzureRM to Az

If your scripts are still based on the AzureRM module, we have several resources to help you with the migration:

- [Get started with migration from AzureRM to Az](migrate-from-azurerm-to-az.md)
- [Full list of breaking changes from AzureRM to Az 1.0.0](migrate-az-1.0.0.md)
- The [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) cmdlet

## Supportability

Az is the most current PowerShell module for Azure. Issues of feature requests can be logged directly on the [github repository](https://github.com/Azure/azure-powershell), or via Microsoft support if you have a support contract.
Feature requests will be implemented in the latest version of Az, critical issues will be implemented on the last two version of Az.

AzureRM will no longer receive new cmdlets or features. However, the AzureRM module is still
officially maintained and will receive critical fixes through February 2020.

## Data collection

Azure PowerShell collects telemetry data by default. Microsoft aggregates collected data to identify patterns of usage to identify common issues and to improve the experience of Azure PowerShell. Microsoft Azure PowerShell does not collect any private or personal data.
For example, the usage data helps identify issues such as cmdlets with low success and helps prioritize our work.

While we appreciate the insights this data provides, we also understand that not everyone wants to send usage data. You can disable data collection with the [`Disable-AzDataCollection`](/powershell/module/az.accounts/disable-azdatacollection) cmdlet. You can also read our [privacy statement](https://privacy.microsoft.com/privacystatement) to learn more.