---
description: This article contains Azure PowerShell versioning, release cadence, and breaking change information for the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.date: 09/05/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure PowerShell versioning, release cadence, and breaking changes
---

# Azure PowerShell versioning, release cadence, and breaking changes

The Az PowerShell module is a rollup module containing more than 70 generally available (GA) or
stable service modules for managing Azure resources directly from PowerShell.

## Versioning

The Az PowerShell modules follow [Semantic Versioning](https://semver.org/) for version numbering.
Versions of Azure service modules fall into one of three categories:

- Generally available. Modules version 1.0.0 and higher without _preview_ in the version. Adheres to
  breaking change policy.
- Preview. Modules less than version 1.0.0. Don't adhere to breaking change policy.
- Feature preview. Modules version 1.0.0 and higher with _preview_ in the version. Don't adhere to
  breaking change policy.

There are two Az PowerShell rollup modules:

- [Az](https://www.powershellgallery.com/packages/Az/). Installs all GA service modules for managing
  Azure resources.
- [AzPreview](https://www.powershellgallery.com/packages/AzPreview/). Installs all GA and preview
  modules for managing Azure resources. Doesn't include feature preview modules.

The AzPreview module is always the same version and is released at the same time as the Az module.

## Release cadence

Planned updates to the Az PowerShell module are released on the first Tuesday of each month. These
12 planned updates per calendar year are in two categories:

- Major versions. At most, two per calendar year introduce breaking changes. The first number in the
  version number is updated. For example, version 6.6.0 to version 7.0.0.
- Minor versions. 10 per calendar year that don't introduce breaking changes. The second number in
  the version number is updated. For example, version 7.0.0 to version 7.1.0.

> [!WARNING]
> Before upgrading to a major breaking change version of the Az PowerShell module, you should
> [**review the migration guide**](https://aka.ms/azps-migration-latest).

Unplanned patch versions may be released at any time to fix bugs. Patch versions don't introduce
breaking changes. The third number in the version number is updated. For example, version 6.2.0 to
version 6.2.1.

## Breaking changes

> [!IMPORTANT]
> Breaking changes may occur at any point for non-GA preview and feature preview modules. Non-GA
> modules aren't required to adhere to breaking change policies.

### When do breaking changes occur

We release two breaking change versions per year:

- One in late spring
- One in the fall

For information about upcoming breaking change releases, see [Azure PowerShell milestones](https://github.com/Azure/azure-powershell/milestones).

### Types of breaking changes

Various types of breaking changes can occur in cmdlets. For more information, see
[Breaking Change Definition](https://github.com/Azure/azure-powershell/blob/preview/documentation/breaking-changes/breaking-changes-definition.md).

### List of breaking changes

For detailed information about breaking changes in major releases of the Az PowerShell module, see
the following articles.

- [AZ 10.0.0 breaking changes](migrate-az-10.0.0.md)
- [AZ 9.0.1 breaking changes](migrate-az-9.0.1.md)
- [Az 8.0.0 breaking changes](migrate-az-8.0.0.md)
- [Az 7.0.0 breaking changes](migrate-az-7.0.0.md)
- [Az 6.0.0 breaking changes](migrate-az-6.0.0.md)
- [Az 5.0.0 breaking changes](migrate-az-5.0.0.md)
- [Az 4.1.0 breaking changes](migrate-az-4.1.0.md)
- [Az 3.0.0 breaking changes](migrate-az-3.0.0.md)
- [Az 2.0.0 breaking changes](migrate-az-2.0.0.md)

### Breaking change warning messages

Breaking change warning messages allow Azure PowerShell cmdlet author's to communicate upcoming
breaking changes with end users.

### Suppress breaking change warning messages

To suppress breaking change warning messages, see
[How do I disable breaking change warning messages in Azure PowerShell?](/powershell/azure/faq#how-do-i-disable-breaking-change-warning-messages-in-azure-powershell-).

For more information, see
[Breaking Changes Attribute Help](https://github.com/Azure/azure-powershell/blob/preview/documentation/breaking-changes/breaking-changes-attribute-help.md#supress-the-breaking-change-messages-at-runtime).

## Provide feedback

- For general feedback, use the [`Send-Feedback`](/powershell/module/azurerm.profile/send-feedback) cmdlet.
- For product issues, log an [issue in the azure-powershell GitHub repository](https://github.com/Azure/azure-powershell/issues).

## Other resources

- [Azure PowerShell modules](https://github.com/Azure/azure-powershell/blob/main/documentation/azure-powershell-modules.md).
- [Azure PowerShell Support Lifecycle](azureps-support-lifecycle.md)
- [Azure PowerShell releases demystified](https://techcommunity.microsoft.com/t5/azure-tools-blog/azure-powershell-releases-demystified/ba-p/1609863)
