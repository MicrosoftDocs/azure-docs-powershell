---
description: Using Az Predictor for intelligent context-aware command completion in Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Intelligent context-aware command completion with Az Predictor
---

# Intelligent context-aware command completion with Az Predictor

## Overview

[Az Predictor][azpredictor-psgallery] is a PowerShell module that provides intelligent,
context-aware suggestions for command completion when using Azure PowerShell. It helps you navigate
the cmdlets and parameters of the [Az PowerShell module][install-azps] more efficiently.

Az Predictor is built on the [subsystem plugin model][subsystem-plugin-model] available in
PowerShell 7.2 and higher and requires [PSReadLine 2.2.2][psreadline-psgallery] or higher to display
suggestions.

## Prerequisites

To use Az Predictor, ensure you have the following:

- [PowerShell version 7.2][install-pwsh] or higher
- [PSReadline version 2.2.2][psreadline-psgallery] or higher

You can install the latest version of **PSReadLine** using:

```powershell
Install-Module -Name PSReadline
```

## Getting started

### Install Az Predictor

Install the **Az.Tools.Predictor** PowerShell module

```powershell
Install-Module -Name Az.Tools.Predictor
```

### Enable Az Predictor

Enable Az Predictor for the current and future PowerShell sessions.

```powershell
Enable-AzPredictor -AllSession
```

### Set your preferred suggestion view

- Enable list view:

  ```powershell
  Set-PSReadLineOption -PredictionViewStyle ListView
  ```

- Enable inline view:

  ```powershell
  Set-PSReadLineOption -PredictionViewStyle InlineView
  ```

> [!NOTE]
> You can switch between the view modes using the <kbd>F2</kbd> key.

## Uninstallation

To uninstall the **Az.Tools.Predictor** module, follow these steps:

1. Close **all** active PowerShell sessions, including those in VS Code.

1. Start a new PowerShell session without loading any profiles:

   ```powershell
   pwsh -noprofile
   ```

1. Uninstall the Az Predictor module

   ```powershell
   Uninstall-Module -Name Az.Tools.Predictor -Force
   ```

1. Close the PowerShell session

## Privacy and data collection

### Privacy

Az predictor uses the previous two Az cmdlets to make suggestions and ignores any cmdlet that's not
part of the [Az PowerShell module][install-azps]. Only the names of cmdlets and parameters are sent
to our API to obtain the suggestion. Parameter values are discarded. The resource group name and
location used are kept locally and reused with subsequent cmdlets for convenience but are never sent
to the API. In the preview version, the module generates and sends anonymized information about the
current session used for predictions to the API. This information is used to assess the quality of
suggestions.

### Data collection

The current version of Az Predictor collects anonymized information about its usage to identify
common issues and improve the experience of future releases. Az Predictor doesn't collect any
private or personal data.

For example, the usage data helps identify inaccurate suggestions and issues like interferences with
PSReadLine. While we appreciate the insights this data provides, we understand not everyone wants to
send usage data. You can disable data collection with the
[Disable-AzDataCollection][disable-azdatacollection] cmdlet. You can also read our
[privacy statement][privacy-statement] to learn more.

<!-- link references -->

[azpredictor-psgallery]: https://www.powershellgallery.com/packages/Az.Tools.Predictor/
[install-azps]: install-azure-powershell.md
[subsystem-plugin-model]: /powershell/scripting/learn/experimental-features#pssubsystempluginmodel
[psreadline-psgallery]: https://www.powershellgallery.com/packages/PSReadLine/
[install-pwsh]: /powershell/scripting/install/installing-powershell
[disable-azdatacollection]: /powershell/module/az.accounts/disable-azdatacollection
[privacy-statement]: https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409
