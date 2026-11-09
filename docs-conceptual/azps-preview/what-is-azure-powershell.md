---
description: Learn what the next-generation Azure PowerShell preview is, how its Az modules manage Azure resources, and how it differs from the AzPreview module.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: overview
ms.date: 11/09/2026
title: Azure PowerShell preview overview
ai-usage: ai-assisted
---

# What is Azure PowerShell (preview)?

Azure PowerShell is the product name for the collection of official Microsoft PowerShell modules for
managing Azure resources. It requires PowerShell, a command-line shell and scripting language.

The next-generation Azure PowerShell preview builds on these tools with an AI-enhanced command-line
experience and profile-based authentication. It provides intelligent assistance while continuing to
use the same Azure management APIs.

The preview primarily supports interactive command-line use. For supported environments and current
limitations, see [Get started with Azure PowerShell (preview)][azps-get-started].

## The Az PowerShell modules

The preview ships as the **Az** PowerShell module and its Azure service-related modules (`Az.*`).
The **Az** module groups service modules, such as **Az.Network** for Azure networking services and
**Az.Aks** for Azure Kubernetes Service.

Azure PowerShell cmdlets call Azure APIs and return .NET objects that you can work with in PowerShell
pipelines.

## Coexistence with existing Azure PowerShell

The preview can be installed alongside existing Azure PowerShell modules. For guidance on choosing
which version to use, see
[Switch between classic and preview Azure PowerShell][azps-switch].

## The AzPreview PowerShell module

The Azure PowerShell preview described in this documentation isn't the **AzPreview** PowerShell
module.

The **AzPreview** module combines generally available (GA) modules from **Az** with preview service
modules. The next-generation preview instead uses the **Az** and `Az.*` module names.

## Next steps

- [Install the Azure PowerShell preview][azps-install].
- [Get started with Azure PowerShell (preview)][azps-get-started].
- [Manage sign-in profiles in Azure PowerShell (preview)][azps-auth].

<!-- link references -->

[azps-install]: install-azure-powershell.md
[azps-auth]: profile-base-login.md
[azps-get-started]: get-started-azureps.md
[azps-switch]: switch-azps-versions.md