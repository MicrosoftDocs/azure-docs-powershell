---
description: Overview of the Az.Tools.Installer PowerShell module developed and maintained by the Azure PowerShell team but not part of the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: overview
title: Overview of the Az.Tools.Installer PowerShell module
---

# Overview of the Az.Tools.Installer PowerShell module

Azure PowerShell is vital for automation and scripting within the Azure environment, accommodating
fast and iterative processes. Customers usually update their Azure PowerShell modules via
**PowerShellGet**, but they experience several challenges due to the intricate dependency
relationships among the modules. Notably, each sub-module relies on **Az.Accounts**, complicating
the update and uninstallation procedures.

**Az.Tools.Installer** emerged to address these issues, offering a more intuitive set of cmdlets for
module management, which includes installation, uninstallation, and updating commands, thereby
streamlining the user experience.

## Benefits of using Az.Tools.installer

**Az.Tools.Installer** boasts significant enhancements based on user feedback, refining its
functionality.

- **Installation:** The module allows users to specify exact versions and manage both stable and
  preview modules. It also supports installation from a NuGet package via a direct URL or local
  path.

- **Uninstallation:** Simplified syntax and the ability to exclude certain modules or focus on
  preview modules alone make the process more user-friendly.

- **Update management:** Allows you to specify the update source repository and the option to keep
  previous versions if needed.

### Performance and user experience improvements

The performance of **Az.Tools.Installer** is significantly optimized, especially on PowerShell 7.x,
with a reduction in installation time by approximately 50%. This optimization is critical for
environments like Azure Functions where installation speed is a concern. A progress bar and detailed
debug information have also been added to enhance user interaction and feedback.

## Getting started with the Az.Tools.Installer module

To start using **Az.Tools.Installer**, install the module with the command
`Install-module -Name Az.Tools.Installer` and then use `Install-AzModule` to set up Azure
PowerShell. Feedback and issues can be [reported through GitHub][azps-repo], which aids in continual
improvement.

<!-- link references -->

[azps-repo]: https://github.com/Azure/azure-powershell
