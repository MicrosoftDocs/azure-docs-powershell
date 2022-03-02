---
description: This article contains Azure PowerShell versioning and release cadence information for the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.date: 03/01/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure PowerShell module versioning and release cadence
---

# Azure PowerShell module versioning and release cadence

The Az PowerShell module is a rollup module containing more than seventy generally available (GA) or
stable service modules for managing Azure resources directly from PowerShell.

## Versioning

The Az PowerShell modules follow [Semantic Versioning](https://semver.org/) for version numbering.
Versions of Azure service modules fall into one of three categories:

- Generally available. Modules version 1.0.0 and higher without _preview_ in the version. Adheres to
  breaking change policy.
- Preview. Modules less than version 1.0.0. Do not adhere to breaking change policy.
- Feature preview. Modules version 1.0.0 and higher with _preview_ in the version. Do not adhere to
  breaking change policy.

There are two Az PowerShell rollup modules:

- [Az](https://www.powershellgallery.com/packages/Az/). Installs all GA service modules for managing
  Azure resources.
- [AzPreview](https://www.powershellgallery.com/packages/AzPreview/). Installs all GA and preview
  modules for managing Azure resources. Does not include feature preview modules.

The version of AzPreview module is always the same version and released at the same time as the Az
module.

## Release cadence

Planned updates to the Az PowerShell module are released on the first Tuesday of each month. These
twelve planned updates per calendar year are broken down into two categories:

- Major versions. No more than two per calendar year that introduce breaking changes. The first
  number in the version number is updated. For example, version 6.6.0 to version 7.0.0.
- Minor versions. Ten per calendar year that do not introduce breaking changes. The second number in
  the version number is updated. For example, version 7.0.0 to version 7.1.0.

> [!WARNING]
> Before upgrading to a major breaking change version of the Az PowerShell module, you should
> [**review the migration guide**](https://aka.ms/azps-migration-latest).

Unplanned patch versions may be released at any time to fix bugs. Patch versions do not introduce
breaking changes. The third number in the version number is updated. For example, version 6.2.0 to
version 6.2.1.

> [!IMPORTANT]
> Breaking changes may occur at any point for non-GA preview and feature preview modules. Non-GA
> modules are not required to adhere to breaking change policies.

## Additional resources

- [Azure PowerShell modules](https://github.com/Azure/azure-powershell/blob/main/documentation/azure-powershell-modules.md).
- [Azure PowerShell Support Lifecycle](azureps-support-lifecycle.md)
- [Azure PowerShell releases demystified](https://techcommunity.microsoft.com/t5/azure-tools-blog/azure-powershell-releases-demystified/ba-p/1609863)
