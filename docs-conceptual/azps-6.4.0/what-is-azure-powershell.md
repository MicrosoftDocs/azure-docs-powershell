---
title: What is Azure PowerShell
description: This article is an introduction to Azure PowerShell and its features.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/13/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# What is Azure PowerShell?

Azure PowerShell is a set of cmdlets for managing Azure resources directly from PowerShell. Azure
PowerShell is designed to make it easy to learn and get started with, but provides powerful features
for automation.

## The Az PowerShell module

> [!IMPORTANT]
> The Az PowerShell module is the recommended PowerShell module for managing Azure resources on all
> platforms.

Introduced in 2018, the Az PowerShell module is based on the .NET Standard, and works with
PowerShell 7.0.6 LTS and PowerShell 7.1.3 or higher on all platforms including Windows, macOS, and
Linux. It's also compatible with Windows PowerShell 5.1.

> [!NOTE]
> PowerShell 7.0.6 LTS and PowerShell 7.1.3 or higher is the recommended version of PowerShell for
> use with the Az PowerShell module on all platforms.

You can install the Az PowerShell module locally on Windows, macOS, and Linux. It can also be used
from a browser through [Azure Cloud Shell](/azure/cloud-shell/overview) or
[inside a Docker container](/powershell/azure/azureps-in-docker). For more information, see the
[Azure PowerShell documentation](/powershell/azure/).

## The AzureRM PowerShell module

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

The AzureRM PowerShell module was the first generation of cmdlets to use the Azure Resource Manager
model for managing Azure Resources. The AzureRM PowerShell module is no longer recommended as
deprecation has been announced, new features are no longer being added, and it's not cross platform.
For more information, see
[Overview of the AzureRM PowerShell module](/powershell/azure/azurerm/overview).

## The Azure PowerShell module

> [!IMPORTANT]
> The cmdlets in the Azure PowerShell module are for managing legacy Azure resources that use
> Service Management APIs.

Some of the cmdlets in the Azure PowerShell module have been deprecated and others have been
deprecated for new customers with retirement announced for existing customers as noted on their
corresponding reference documentation pages. For more information, see
[Overview of the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/overview)
