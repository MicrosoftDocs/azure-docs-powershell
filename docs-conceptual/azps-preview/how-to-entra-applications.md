---
title: "Find identities and register a Microsoft Entra application with Azure PowerShell (preview)"
description: "Look up test identities, register a single-tenant Microsoft Entra application, and remove it with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: how-to
ms.date: 10/27/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Find identities and register a Microsoft Entra application with Azure PowerShell (preview)

In this article, you look up test identities, register a single-tenant Microsoft Entra application, and remove it with Azure PowerShell preview.

> [!IMPORTANT]
> These draft examples require end-to-end validation against the release build before use.

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- A test user and a test group in your tenant, with permission to read them through Microsoft Graph and to create application registrations.

Use a new application registration, not an existing application. Do not share tenant-wide user data from list output.

## Set variables

```powershell
$ErrorActionPreference = 'Stop'
$userId = '<test-user-object-ID>'
$groupId = '<test-group-object-ID>'
$run = Get-Date -Format 'yyyyMMddHHmmss'
$appName = "azclips-app-$run"
```

## Find identities

```powershell
Get-AzMsGraphUser -Id $userId
Get-AzMsGraphUser
Get-AzMsGraphGroup -ObjectId $groupId
Get-AzMsGraphGroup
Get-AzMsGraphGroupMember -GroupObjectId $groupId
```

## Register the application

```powershell
$app = New-AzMsGraphApplication -DisplayName $appName -SignInAudience AzureADMyOrg
$appObjectId = $app.Id
```

## Inspect the registration

```powershell
Get-AzMsGraphApplication -Id $appObjectId
Get-AzMsGraphApplication -DisplayName $appName
$clientId = $app.AppId
```

## Clean up resources

```powershell
Remove-AzMsGraphApplication -Id $appObjectId
Get-AzMsGraphApplication -Id $appObjectId
```

The final lookup reports that the application is not found.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Run repeatable deployments from a pipeline](tutorial-pipeline-deployments.md).
