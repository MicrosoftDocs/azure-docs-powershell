---
title: Intercept survey guidance
description: This article contains information about azure powershell intercept survey guidance.
ms.date: 08/31/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
---

# Intercept survey guidance

The purpose of the intercept survey is to collect information about the satisfaction of Azure
command line tools. By providing responses to the survey, you help to identify common issues and
areas for improvement. Understanding your experiences and opinions helps to make future releases of
Azure command line tools better for you and others.

## What data is collected

The intercept survey collects anonymized feedback about your satisfaction of Azure command line
tools. The intercept survey does not collect any private or personal data.

While we appreciate the insights this data provides, we understand not everyone wants to be prompted
to complete a survey. You can disable being prompted to participate in surveys with the
`Update-AzConfig` cmdlet or via an environment variable.

## Disable the survey

In the following example, the `Update-AzConfig` cmdlet is used to disable the survey message.

```azurepowershell
Update-AzConfig -DisplaySurveyMessage $false
```

You can also use the `$Env:AzSurveyMessage` environment variable to disable the survey message.

```azurepowershell
Set-Item -Path Env:\AzSurveyMessage -Value $false
```

## Privacy statement

Your privacy is important to us.
[Microsoft's Privacy Statement](https://privacy.microsoft.com/privacystatement) explains the
personal data Microsoft processes, how Microsoft processes it, and for what purposes.
