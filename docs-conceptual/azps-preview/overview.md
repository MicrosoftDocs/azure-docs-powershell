---
title: Overview of Azure PowerShell
description: An overview of the Azure PowerShell Az module, with information on how to install and get started.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.manager: carmonm
ms.date: 10/29/2018
---
# Overview of Azure PowerShell

Azure PowerShell provides a set of cmdlets that use the [Azure Resource
Manager](/azure/azure-resource-manager/resource-group-overview) model for managing your Azure
resources. You can use it in your browser with [Azure Cloud Shell](/azure/cloud-shell/overview), or
you can install it on your local machine and use it in any PowerShell session.

Use the [Cloud Shell](/azure/cloud-shell/overview) to run the Azure PowerShell in your browser, or
[install](install-az-ps.md) it on own computer. Then read the [Get Started](get-started-azureps.md)
article to begin using it. For information about the latest release, see the
[release notes](release-notes-azureps.md).

## About the new Az module

This documentation describes the new Az module for Azure PowerShell, which is currently in preview. This new module is written from the ground up in .NET Standard,
making it portable and compatible with both PowerShell 5.x on Windows, and PowerShell 6.x on any platform.

Az will become the main module for Azure PowerShell when it reaches version 1.0. Before that time, there's feature parity between `Az`
and the current Azure PowerShell module `AzureRM`. Since Az is in preview, you may experience bugs. If you do, 
[file a GitHub issue](https://github.com/azure/azure-powershell/issues).

To prepare for the module changeover and get all of your scripts up-to-date, we've included some instructions on migrating older scripts to use the new
cmdlet set. In general, the cmdlet names are the same except that any instance of `AzureRM` has been replaced with `Az`. So old commands like `New-AzureRmVM` have become
`New-AzVM`.

For detailed instructions on migrating to the new module, check out [Migrating from AzureRM to Az](__TBD__).

> [!IMPORTANT]
>
> Since the `Az` module is in preview, our documentation in other sections of the site still use the `AzureRM` cmdlet set. You can use `AzureRM`-style cmdlets through
> a compatibility mode that can be enabled with `Enable-AzureRmAlias`. To learn more about aliasing, see [Migrating from AzureRM to Az](__TBD__#aliases).
> If you run your PowerShell scripts in Cloud Shell, `AzureRM` aliases are already enabled for you.

## Common scenarios

The following samples can help you learn how to perform common scenarios with Azure PowerShell:

* [Linux Virtual Machines](/azure/virtual-machines/virtual-machines-linux-powershell-samples?toc=/powershell/azure/toc.json)
* [Windows Virtual Machines](/azure/virtual-machines/virtual-machines-windows-powershell-samples?toc=/powershell/azure/toc.json)
* [Web Apps](/azure/app-service-web/app-service-powershell-samples?toc=/powershell/azure/toc.json)
* [SQL Databases](/azure/sql-database/sql-database-powershell-samples?toc=/powershell/azure/toc.json)

## Learn PowerShell basics

If you're unfamiliar with PowerShell, an introduction may be helpful.

* [Installing PowerShell](/powershell/scripting/setup/installing-windows-powershell)
* [Scripting with PowerShell](/powershell/scripting/powershell-scripting)

You can also watch this video:
[PowerShell Basics: (Part 1) Getting Started with PowerShell](https://channel9.msdn.com/Blogs/Taste-of-Premier/PowerShellBasicsPart1).

Or attend the Microsoft Virtual Academy's [Getting Started with PowerShell Jumpstart](https://mva.microsoft.com/liveevents/powershell-jumpstart).

## Build your skills with Microsoft Learn

- [Automate Azure tasks using scripts with PowerShell](/learn/modules/automate-azure-tasks-with-powershell/)
- [More interactive learning...](/learn/browse/?term=powershell)

## Other Azure PowerShell modules

* [Azure Active Directory](/powershell/azure/active-directory/)
* [Azure Information Protection](/powershell/azure/aip/)
* [Azure Service Fabric](/powershell/azure/service-fabric/)
* [Azure ElasticDB](/powershell/azure/elasticdbjobs/)
