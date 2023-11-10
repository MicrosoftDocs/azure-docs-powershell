---
description: Overview of the Az.Tools.Predictor PowerShell module developed and maintained by the Azure PowerShell team but not part of the Az PowerShell module.
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: overview
title: Overview of the Az.Tools.Predictor PowerShell module
---

# Overview of the Az.Tools.Predictor PowerShell module

The **Az.Tools.Predictor** PowerShell module is designed to streamline Azure command-line
operations. It offers cmdlet suggestions, parameter guidance, and value suggestions by leveraging an
AI-powered recommendation engine to enhance user productivity in Azure environments. By providing an
intelligent, context-aware command completion tool for Azure PowerShell, it significantly reduces
the complexity and improves the accuracy of Azure management tasks. For IT professionals and
developers, this means a more intuitive and less error-prone interface when managing Azure
resources, aligning with the growing trend of AI-powered operational tools in cloud computing.

## How Az.Tools.Predictor enhances PowerShell

The module operates within PowerShell 7.2 or higher using the subsystem plugin model and requires
**PSReadLine** 2.2.2 or above. It integrates seamlessly with the PowerShell environment, providing
context-aware suggestions that adapt as users type commands. The intelligence behind
**Az.Tools.Predictor** is tailored to the user's current context, making its recommendations highly
relevant and time-saving.

## Getting started with Az.Tools.Predictor

To begin using **Az.Tools.Predictor**, users must ensure they have installed the correct PowerShell
and **PSReadLine** version. Following this, the **Az.Tools.Predictor** module can be installed with
the command `Install-Module -Name Az.Tools.Predictor` and enabled for all sessions using
`Enable-AzPredictor -AllSession`. The module supports two view modes for suggestions: an _inline
view_, which is the default showing one suggestion at a time, and a _list view_, which can be
toggled by pressing <kbd>F2</kbd>.

## Privacy and data collection

Privacy is a critical aspect of **Az.Tools.Predictor's** design. It uses the last two cmdlets
entered to generate suggestions, and while it retains the names of cmdlets and parameters, it
discards any parameter values. Resource group names and locations used are stored locally for
convenience. Additionally, the tool collects anonymized data about its usage to improve future
iterations. While we appreciate the insights this data provides, we understand not everyone wants to
send usage data. You can disable data collection with the
[Disable-AzDataCollection][disable-azdatacollection] cmdlet. For more information, see
[our privacy statement][privacy-policy].

<!-- link references -->

[disable-azdatacollection]: /powershell/module/az.accounts/disable-azdatacollection
[privacy-policy]: https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409
