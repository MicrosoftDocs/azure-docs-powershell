---
title: "Find identities and register a Microsoft Entra application with Azure PowerShell (preview)"
description: "Look up test identities, register a single-tenant Microsoft Entra application, and remove it with Azure PowerShell preview."
author: msmbaldwin
ms.author: mbaldwin
ms.service: azure-powershell
ms.topic: how-to
ms.date: 10/28/2026
ms.custom: devx-track-azurepowershell
ai-usage: ai-assisted
---

# Find identities and register a Microsoft Entra application with Azure PowerShell (preview)

In this article, you use Azure PowerShell preview to find the right users and groups in your tenant, and then register an application for them to use.

By the end of this article, you've found the intended user, group, and group membership, created a single-tenant application registration with the settings you chose, and removed that registration.

## Prerequisites

- PowerShell 7.6 or later. Use a fresh session without classic Az modules loaded.
- Azure PowerShell preview, installed and signed in as described in [Set up and switch sign-in profiles](quickstart-profiles.md).
- A test user and a test group in your tenant, with permission to read them through Microsoft Graph and to create application registrations.

Use a new application registration, not an existing application. Don't share tenant-wide user data from list output.

## Get the user and group object IDs

The commands in this article identify the test user and group by their object IDs. To find an object ID in the [Microsoft Entra admin center](https://entra.microsoft.com), go to **Entra ID** > **Users** or **Entra ID** > **Groups**, select the user or group, and then copy the **Object ID** value from the **Overview** page.

You can also look up the object IDs with Azure PowerShell preview. Replace the placeholders with the test user's email address and the test group's display name:

```powershell
Get-AzMsGraphUser -Mail '<test-user-email>' -Select id, displayName
Get-AzMsGraphGroup -DisplayName '<test-group-display-name>' -Select id, displayName
```

Each command returns the matching object with its `id`, which is the object ID, and its display name. If a command returns more than one object, choose the one you intend to use.

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

`Get-AzMsGraphUser -Id` returns the test user, and `Get-AzMsGraphGroup -ObjectId` returns the test group. Without parameters, `Get-AzMsGraphUser` and `Get-AzMsGraphGroup` list the users and groups in your tenant. `Get-AzMsGraphGroupMember` lists the direct members of the test group. If the test user is a member of the group, the user appears in that list.

## Register the application

```powershell
$app = New-AzMsGraphApplication -DisplayName $appName -SignInAudience AzureADMyOrg
$appObjectId = $app.Id
$clientId = $app.AppId
```

`New-AzMsGraphApplication` creates the registration and returns it, including a generated object ID and application (client) ID. `AzureADMyOrg` means that only accounts in your tenant can sign in to the application.

## Inspect the registration

```powershell
Get-AzMsGraphApplication -Id $appObjectId
(Get-AzMsGraphApplication -DisplayName $appName | Measure-Object).Count
```

The first command shows the display name you chose, the client ID in `$clientId`, and the sign-in audience `AzureADMyOrg`. The second command returns `1`, because exactly one registration has that display name.

## Clean up resources

```powershell
Remove-AzMsGraphApplication -Id $appObjectId
Get-AzMsGraphApplication -DisplayName $appName
```

`Remove-AzMsGraphApplication` doesn't return output. The `Get-AzMsGraphApplication` command returns no output, which confirms that no registration with that display name remains. Directory changes can take a short time to replicate. If the registration still appears, wait a minute and run the `Get-AzMsGraphApplication` command again.

Microsoft Graph soft-deletes the registration, so it can be restored for 30 days before it's permanently deleted.

## Related content

- For more information, see [Get started with the preview](getting-started.md).
- For more information, see [Set up and switch sign-in profiles](quickstart-profiles.md).
- For more information, see [Run repeatable deployments from a pipeline](tutorial-pipeline-deployments.md).
