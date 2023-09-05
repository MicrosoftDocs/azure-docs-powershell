---
description: This article is an introduction to Azure PowerShell and its features.
ms.custom: devx-track-azurepowershell
ms.date: 09/05/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: overview
title: What is Azure PowerShell
---

# What is Azure PowerShell?

Azure PowerShell is a set of cmdlets for managing Azure resources directly from PowerShell. Azure
PowerShell is designed to make it easy to learn and get started with, but provides powerful features
for automation.

## The Az PowerShell module

> [!IMPORTANT]
> The Az PowerShell module is the recommended PowerShell module for managing Azure resources on all
> platforms.

The Az PowerShell module is based on the .NET Standard, and works with PowerShell 7.0.6 LTS and
PowerShell 7.1.3 or higher on all platforms including Windows, Linux, and macOS. It's also
compatible with Windows PowerShell 5.1.

> [!NOTE]
> PowerShell 7.0.6 LTS and PowerShell 7.1.3 or higher is the recommended version of PowerShell for
> use with the Az PowerShell module on all platforms.

You can install the Az PowerShell module locally on Windows, Linux, and macOS. It can also be used
from a browser through [Azure Cloud Shell](/azure/cloud-shell/overview) or
[inside a Docker container](/powershell/azure/azureps-in-docker). For more information, see the
[Azure PowerShell documentation](/powershell/azure/).

### Authentication

Azure PowerShell supports several authentication methods. For detailed information about
authenticating to Azure from the Az PowerShell module, see
[Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

### Module Design

The Az PowerShell module is a wrapper module for Azure service related PowerShell modules, usually
one module per Azure service such as `Az.Network` for Azure networking services and `Az.AKS` for
Azure Kubernetes Service.

The cmdlets in the Az PowerShell module make REST calls to the Azure API. Breaking changes in the Az
PowerShell module are limited to twice a year. Many breaking changes at the API level are handled
within the cmdlets to prevent the perception of a breaking change.

The Az PowerShell module contains cmdlets for performing both control plane and data plane
operations in Azure. You use the control plane to manage resources in your subscription. You use the
data plane to use capabilities exposed by your instance of a resource type. For more information,
see
[Azure control plane and data plane](/azure/azure-resource-manager/management/control-plane-and-data-plane).

### Output Objects

The cmdlets in the Az PowerShell module produce .NET objects. As with any PowerShell command that
produces output, the cmdlets in the Az PowerShell module can be piped to the
[Get-Member](/powershell/module/microsoft.powershell.utility/get-member) cmdlet to determine what
type of object is produced along with a list of the available properties and methods. For more
information, see [Query output of Azure PowerShell](/powershell/azure/queries-azureps) and
[Format Azure PowerShell cmdlet output](/powershell/azure/formatting-output).

## Other modules

The AzureAD and MSOnline PowerShell modules aren't part of the Az PowerShell module. For more
information about those modules, see the documentation for
[Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/overview).

## Legacy Azure PowerShell modules

### The AzureRM PowerShell module

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

The AzureRM PowerShell module is no longer recommended as deprecation has been announced, new
features are no longer being added, and it's not cross platform. For more information, see
[Overview of the AzureRM PowerShell module](/powershell/azure/azurerm/overview).

### The Azure PowerShell module

> [!IMPORTANT]
> The cmdlets in the Azure PowerShell module are for managing legacy Azure resources that use
> Service Management APIs.

Some cmdlets in the Azure PowerShell module have been deprecated and others have been deprecated for
new customers with retirement announced for existing customers as noted on their corresponding
reference documentation pages. For more information, see
[Overview of the Azure PowerShell Service Management module](/powershell/azure/servicemanagement/overview)
