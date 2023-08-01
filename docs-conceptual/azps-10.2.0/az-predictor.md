---
description: Using Az Predictor for intelligent context-aware command completion in Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 08/01/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Intelligent context-aware command completion with Az Predictor
---

# Intelligent context-aware command completion with Az Predictor

## Overview

[Az Predictor](https://www.powershellgallery.com/packages/Az.Tools.Predictor/) is a PowerShell
module that helps you navigate the cmdlets and parameters of the
[Az PowerShell module](https://www.powershellgallery.com/packages/Az). It provides intelligent
context-aware suggestions for command completion when using Azure PowerShell.

Az Predictor uses the
[subsystem plugin model](/powershell/scripting/learn/experimental-features#pssubsystempluginmodel)
available in PowerShell 7.2. This updated version requires
[PSReadLine 2.2.2](https://www.powershellgallery.com/packages/PSReadLine/2.2.2) or higher to display
suggestions.

## Requirements

Required configuration for Az Predictor:

- [PowerShell 7.2](https://github.com/PowerShell/PowerShell/) or higher
- [PSReadline 2.2.2](https://github.com/PowerShell/PSReadLine/) or higher

Install the latest version of PSReadLine:

```powershell
Install-Module -Name PSReadline
```

## Getting started

### Install Az Predictor

Install the Az.Tools.Predictor PowerShell module

```powershell
Install-Module -Name Az.Tools.Predictor
```

### Enable Az Predictor

1. Enable Az Predictor for the current and future PowerShell sessions.

   ```powershell
   Enable-AzPredictor -AllSession
   ```

1. Set your preferred view for suggestions.

   Enable list view:

   ```powershell
   Set-PSReadLineOption -PredictionViewStyle ListView
   ```

   Enable inline view:

   ```powershell
   Set-PSReadLineOption -PredictionViewStyle InlineView
   ```

> [!NOTE]
> You can switch between view modes with the <kbd>F2</kbd> key.

## Uninstallation

Once installed and enabled, Az Predictor is loaded in the PowerShell profile.
To uninstall the Az.Tools.Predictor module:

1. Close **all** PowerShell sessions including VS Code.

1. Launch a PowerShell session with no profile.

   ```powershell
   pwsh -noprofile
   ```

1. Uninstall Az Predictor

   ```powershell
   Uninstall-Module -Name Az.Tools.Predictor -Force
   ```

1. Close PowerShell

## Privacy and data collection

### Privacy

Az predictor uses the previous two Az cmdlets to make suggestions and ignores any cmdlet that's not
part of the [Az PowerShell](https://www.powershellgallery.com/packages/Az) module. Only the names of
cmdlets and parameters are sent to our API to obtain the suggestion. Parameter values are discarded.
The resource group name and location used are kept locally and reused with subsequent cmdlets for
convenience but are never sent to the API. In the preview version, the module generates and sends
anonymized information about the current session used for predictions to the API. This information
is used to assess the quality of suggestions.

### Data collection

The current version of Az Predictor collects anonymized information about its usage to identify
common issues and improve the experience of future releases. Az Predictor doesn't collect any
private or personal data.

For example, the usage data helps identify inaccurate suggestions and issues like interferences with
PSReadLine. While we appreciate the insights this data provides, we understand not everyone wants to
send usage data. You can disable data collection with the
[Disable-AzDataCollection](/powershell/module/az.accounts/disable-azdatacollection)
cmdlet. You can also read our
[privacy statement](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409) to learn more.
