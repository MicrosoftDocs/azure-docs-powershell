---
description: This article is an introduction to Azure PowerShell and its features.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: overview
title: What is Azure PowerShell
---

# What is Azure PowerShell?

Azure PowerShell is the product name for the collection of official Microsoft PowerShell modules for
managing Azure resources. It requires PowerShell, a command-line shell and scripting language.

You can use Azure PowerShell interactively by running commands from PowerShell or creating and
executing scripts that consist of multiple commands.

## The Az PowerShell module

The current version of Azure PowerShell is the **Az** PowerShell module. It's the recommended
PowerShell module for managing Azure resources with PowerShell on all platforms including Windows,
Linux, and macOS. It includes thousands of commands that control almost every aspect of Azure. The
**Az** PowerShell module is cross-platform.

> [!NOTE]
> PowerShell 7 or higher is the recommended version of PowerShell for use with the Az PowerShell
> module. It's also compatible with Windows PowerShell 5.1.

There are a few different options for using the Az PowerShell module:

- [Azure Cloud Shell][cloud-shell]: A browser-based shell that allows you to run Azure PowerShell
  commands without installing anything on your local machine.
- [Local installation][azps-install]: To run commands directly from your terminal, install Azure
  PowerShell on your local machine.
- [Docker container][azps-docker]: Run Azure PowerShell in a Docker container.

### Authentication

Azure PowerShell supports several authentication methods. For detailed information about
authenticating to Azure from the Az PowerShell module, see
[Sign into Azure from Azure PowerShell][azps-auth].

### Module Design

The **Az** PowerShell module is a wrapper module for Azure service-related PowerShell modules,
usually one module per Azure service, such as **Az.Network** for Azure networking services and
**Az.Aks** for Azure Kubernetes Service.

The cmdlets in the **Az** PowerShell module make REST calls to the Azure Resource Manager API.
Breaking changes in the **Az** PowerShell module are limited to twice a year. Many breaking changes
at the API level are handled within the cmdlets to prevent the perception of a breaking change.

The **Az** PowerShell module contains cmdlets for performing both control plane and data plane
operations in Azure. You use the control plane to manage resources in your subscription. You use the
data plane to control capabilities exposed by your instance of a resource type. For more
information, see [Azure control plane and data plane][control-and-data-plane].

### Output Objects

The cmdlets in the **Az** PowerShell module produce .NET objects. As with any PowerShell command
that produces output, the cmdlets in the **Az** PowerShell module can be piped to the `Get-Member`
cmdlet to determine what type of object is produced, along with a list of the available properties
and methods. For more information, see [Query output of Azure PowerShell][azps-output] and
[Format Azure PowerShell cmdlet output][format-azps-output].

## The AzPreview PowerShell module

The **AzPreview** PowerShell module includes all generally available (GA) modules from the **Az**
PowerShell module and all preview modules for managing Azure resources. It isn't recommended for use
in production environments since preview modules don't adhere to breaking change policies.

The **AzPreview** module is always the same version and is released at the same time as the **Az**
PowerShell module.

## The AzureRM PowerShell module

While you might find examples online that use the **AzureRM** PowerShell module, it's the previous
generation of Azure PowerShell. It's deprecated, no longer maintained or supported, and not
recommended. Commands in the **AzureRM** PowerShell module use the `*-AzureRM*` format. For more
information, see [Overview of the AzureRM PowerShell module][azurerm-module].

## The Azure PowerShell module

You might also encounter a version of Azure PowerShell named the **Azure** PowerShell module. This
module is for managing legacy Azure resources that use Azure Service Manager (ASM) APIs. It isn't
recommended for creating new resources as ASM is scheduled for retirement. For more information, see
[Azure Service Manager retirement][azure-asm-retirement].

## Azure-related PowerShell modules

These products are used to manage Azure resources but aren't part of the Azure PowerShell collective
product. They should never be described using the "Azure PowerShell" collective name.

- Azure Active Directory PowerShell (AzureAD)
- Azure Information Protection PowerShell
- Azure Deployment Manager PowerShell
- Azure Elastic Database Jobs PowerShell
- Azure Service Fabric PowerShell
- Azure Stack PowerShell
- Microsoft.Graph PowerShell
- Microsoft.Graph.Entra PowerShell
- MSOnline PowerShell

Guidelines

- Always use the full proper name of the product or the specific PowerShell module name

## References

[Get-Member][get-member]

<!-- link references -->

[cloud-shell]: /azure/cloud-shell/overview
[azps-install]: install-azure-powershell.md
[azps-docker]: azureps-in-docker.md
[azps-auth]: /powershell/azure/authenticate-azureps
[control-and-data-plane]: /azure/azure-resource-manager/management/control-plane-and-data-plane
[get-member]: /powershell/module/microsoft.powershell.utility/get-member
[azps-output]: queries-azureps.md
[format-azps-output]: formatting-output.md
[azurerm-module]: /previous-versions/powershell/azure/
[azure-asm-retirement]: /azure/azure-resource-manager/management/asm-retirement
