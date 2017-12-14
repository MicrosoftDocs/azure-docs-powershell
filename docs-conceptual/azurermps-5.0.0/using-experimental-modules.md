---
title: Using experimental Azure PowerShell modules
description: Understand the philosophy and usage of experimental Azure PowerShell modules.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/05/2017
---
# Using experimental Azure PowerShell modules

With the emphasis on developer tools (especially CLIs) in Azure, the Azure PowerShell team is
experimenting with many improvements to the Azure PowerShell experience.

## Experimentation methodology

To facilitate experimentation, we are creating new Azure PowerShell modules that implement existing
Azure SDK functionality in new, easier to use ways. In most cases, the cmdlets exactly mirror
existing cmdlets. However, the experimental cmdlets provide a shorthand notation and smarter default
values that make it easier to create and manage Azure resources.

These modules can be installed side-by-side with existing Azure PowerShell modules. The cmdlet
names have been shortened to provide shorter names and avoid name conflicts with existing,
non-experimental cmdlets.

The experimental modules use the following naming convention: `AzureRM.*.Experiments`. This naming
convention is similar to the naming of Preview modules: `AzureRM.*.Preview`. Preview modules differ
from experimental modules. Preview modules implement new functionality of Azure services that is
only available as a Preview offering. Preview modules replace existing Azure PowerShell modules and
use the same cmdlet and parameter names.

## How to install an experimental module

Experimental modules are published to the PowerShell Gallery just like the existing Azure
PowerShell modules. To see a list of experimental modules, run the following command:

```powershell
Find-Module AzureRM.*.Experiments
```

```Output
Version Name                         Repository Description
------- ----                         ---------- -----------
1.0.25  AzureRM.Compute.Experiments  PSGallery  Azure Compute experiments for VM creation
1.0.0   AzureRM.Websites.Experiments PSGallery  Create and deploy web applications using Azure App Services.
```

To install the experimental module, use the following commands from an elevated PowerShell session:

```powershell
Install-Module AzureRM.Compute.Experiments
Install-Module AzureRM.Websites.Experiments
```

### Documentation and support

Documentation is included in the install package and is accessed using the `Get-Help` cmdlet. No
official documentation is published for experimental modules.

We encourage you to test these modules. Your feedback allows us to improve usability and respond to
your needs. However, being experimental, support for these modules is limited. Questions or problem
reports can be submitted by creating an [issue](https://github.com/Azure/azure-powershell/issues)
in the GitHub repository.

## Experiments and areas of improvement

These improvements were selected based on key differentiators in competing products. For example,
Azure CLI 2.0 has made a point of basing commands on _scenarios_ rather than _API surface area_.
Azure CLI 2.0 use a number of smart defaults that make "getting started" scenarios easier for end
users.

### Core improvements

The core improvements are regarded as "common sense", and little experimentation is needed to move
forward in implementing these updates.

- Scenario-based Cmdlets - **All*- cmdlets should be designed around scenarios, not the Azure REST
  service.

- Shorter Names - Includes the names of cmdlets (for example, `New-AzureRmVM` => `New-AzVm`) and the
  names of parameters (for example, `-ResourceGroupName` => `-Rg`). Use aliases for compatibility with
  "old" cmdlets. Provide _backwards compatible_ parameter sets.

- Smart Defaults - Create smart defaults to fill in "required" information. For example:
  - Resource Group
  - Location
  - Dependent resources

### Experimental improvements

The experimental improvements present a significant change that the team wants to validate via
experimentation.

- Simple types - Create scenarios should move away from complex types and config objects. Simplify
  the configuration down to one or two parameters.

- "Smart Create" - All create scenarios implementing "Smart Create" would have _no_ required
  parameters: all necessary information would be chosen by Azure PowerShell in an opinionated
  fashion.

- Gray Parameters - In many cases, some parameters could be "gray" or semi-optional. If the
  parameter is not specified, the user is asked if they want the parameter generated for them. It
  also makes sense for gray parameters to infer a value based on context with the user's consent.
  For example, it may make sense to have the gray parameter suggest the most recently used value.

- `-Auto` Switch - The `-Auto` switch would provide an "opt-in" way for users to _default all the
  things_ while maintaining the integrity of required parameters in the mainline path.

### Feature-specific switches

For example, the "Create web app" scenario might have a `-Git` or `-AddRemote` switch that would
automatically add an "azure" remote to an existing git repository.

- Settable Defaults - Users should have the ability to default certain ubiquitous parameters like
  `-ResourceGroupName` and `-Location`.

- Size Defaults - Resource "sizes" can be confusing to users since many Resource Providers use
  different names (for example, "Standard\_DS1\_v2" or "S1"). However, most users care more about
  cost. Therefore, it makes sense to define "universal" sizes based on a pricing schedule. Users
  can choose a specific size or let Azure PowerShell choose the _best option_ based on the resource
  the budget.

- Output Format - Azure PowerShell currently returns `PSObject`s and there is little console
  output. Azure PowerShell may need to display some information to the user regarding the "smart
  defaults" used.
