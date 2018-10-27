---
title: Introducing the Azure PowerShell Az module
description: Introducing the new Azure PowerShell module Az, the replacement for the AzureRM module.
ms.date: 10/22/2018
author: sptramer
ms.author: sttramer
ms.manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
---
# Introducing the new Azure PowerShell Az module

Starting in November 2018, the Azure PowerShell module `Az` is in full public preview and all users are recommended to switch. This module is an improvement in the stability and portability of the old `AzureRM` module, offering feature parity and an easy migration path through familiar, but shorter, cmdlet names.

`Az` is written using the capabilities of the fully portable .NET Standard library, which means that it runs under both PowerShell 5.x and PowerShell Core, on any platform. Maintenance will be easier for Microsoft engineers while keeping the impact on users low and unifying the code base and distribution of Azure PowerShell for all platforms.

Since this is a brand-new module, the versioning has been reset. The first stable version will be 1.0.

## Upgrade to Az

All users should upgrade to the new `Az` module. To do so:

* [Uninstall the Azure PowerShell AzureRM module](/powershell/azure/uninstall-azurerm-ps?view=azurermps-6.11.0)
* [Install the Azure PowerShell Az module](/powershell/azure/install-azurerm-ps?view=azureazps-0.5.0)
* While conducting your migration, enable the `AzureRM` compatibility aliases with `Enable-AzureRMAlias`.

## Migrate existing scripts to Az

While `Az` is designed to make migrations easy, we know that any change like this is never ideal for users. To help you update your scrips to use this new module, we have the following materials on migration:

* Enable the `AzureRM` compatibility mode with `Enable-AzureRMAlias`, and ensure that your scripts work as expected.
* __TBD__

For a full description of the migration process, including an example, see __TBD__.

## Maintenance of AzureRM

The existing `AzureRM` module will go into maintenance mode when `Az` hits version 1.0. This means that the module will receive bug fixes that are considered important, but will not be getting new features. To keep up with the latest Azure services and features, make sure that you switch over to the `Az` module as soon as possible.
