---
description: Learn what the next-generation Azure PowerShell preview is and how its Az modules manage Azure resources.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: overview
ms.date: 11/12/2026
title: Azure PowerShell preview overview
ai-usage: ai-assisted
---

# What is Azure PowerShell (preview)?

Azure PowerShell is the product name for the collection of official Microsoft PowerShell modules for
managing Azure resources. It requires PowerShell, a command-line shell and scripting language.

The next-generation Azure PowerShell preview builds on these tools with an AI-enhanced command-line
experience and profile-based authentication. It provides intelligent assistance while continuing to
use the same Azure management APIs.

For supported environments and current
limitations, see [Get started with Azure PowerShell (preview)][azps-get-started].

## The Az PowerShell modules

The next-generation Azure PowerShell preview ships as the **Az** PowerShell module and its Azure
service-related modules (`Az.*`).
The **Az** module groups service modules, such as **Az.Network** for Azure networking services and
**Az.Aks** for Azure Kubernetes Service.

Azure PowerShell cmdlets call Azure APIs and return .NET objects that you can work with in
PowerShell pipelines.

## Coexistence with existing Azure PowerShell

The preview can be installed alongside existing Azure PowerShell modules. For guidance on choosing
which version to use, see
[Switch between classic and preview Azure PowerShell][azps-switch].

## Existing and next-generation Azure PowerShell

The next-generation Azure PowerShell preview and your existing Azure PowerShell use the same module names (`Az`, `Az.Compute`, and so on), so a session can load only one of them.

### Identify the loaded version

```powershell
Get-Module Az -ListAvailable | Select-Object Name, Version, ModuleBase
Get-Module Az | Select-Object Name, Version
```

A version in the `0.1.x` series means the preview is loaded. A higher version means your existing modules are loaded. Without a version, `Import-Module Az` loads the highest installed version, which is your existing version when it's present.

### Differences from the existing Azure PowerShell

- **Coverage:** Not all Azure PowerShell and Azure CLI scenarios are available.
- **Cmdlets and output:** The preview aims to keep cmdlets close to your existing Azure PowerShell, but they aren't guaranteed to be identical. Check the cmdlet help in the preview, and compare your results with the expected output in each article.
- **Sign-in:** The preview doesn't share sign-in context or tokens with your existing Azure PowerShell, so you sign in again. It uses [profile-based authentication][azps-auth] and opens a browser by default. These sign-in methods aren't available yet:
  - Broker sign-in, such as Web Account Manager on Windows
  - Resource Owner Password Credentials (ROPC), such as `Connect-AzAccount -Credential`

### Preview expectations

New capabilities are added frequently. Between preview releases, cmdlets, output, and behavior might change, including changes that might break existing scripts. If something doesn't work as documented, [open an issue in the GitHub repository](https://github.com/Azure/azclips/issues).

To choose which version loads, see [Switch between classic and preview Azure PowerShell][azps-switch].

## Next steps

- [Install the Azure PowerShell preview][azps-install].
- [Get started with Azure PowerShell (preview)][azps-get-started].
- [Manage sign-in profiles in Azure PowerShell (preview)][azps-auth].

<!-- link references -->

[azps-install]: install-azure-powershell.md
[azps-auth]: profile-base-login.md
[azps-get-started]: get-started-azureps.md
[azps-switch]: switch-azps-versions.md