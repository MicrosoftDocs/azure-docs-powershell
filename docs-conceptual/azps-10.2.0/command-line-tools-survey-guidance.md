---
description: This article contains guidance about the Azure command line tools survey.
ms.custom: devx-track-azurepowershell
ms.date: 08/01/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure command line tools survey guidance
---

# Azure command line tools survey guidance

When using Azure PowerShell, you may be invited to participate in a survey to tell us about your
experience. By responding to the survey, you help to identify common issues and areas for
improvement. Understanding your experiences and opinions helps to make future releases of Azure
command line tools better for you and others.

## What data is collected

The survey collects anonymized feedback about your satisfaction with Azure command line tools and
doesn't collect any private or personal data.

While we appreciate the insights this data provides, we understand not everyone wants to be prompted
to complete a survey. You can disable being prompted to participate in surveys with the
`Update-AzConfig` cmdlet or via an environment variable.

## Disable the survey

In the following example, the `Update-AzConfig` cmdlet is used to disable the survey message.

```azurepowershell-interactive
Update-AzConfig -DisplaySurveyMessage $false
```

You can also use the `$Env:AzSurveyMessage` environment variable to disable the survey message.

```azurepowershell-interactive
Set-Item -Path Env:\AzSurveyMessage -Value $false
```

## Privacy statement

Your privacy is important to us.
[Microsoft's Privacy Statement](https://privacy.microsoft.com/privacystatement) explains the
personal data Microsoft processes, how Microsoft processes it, and for what purposes.
