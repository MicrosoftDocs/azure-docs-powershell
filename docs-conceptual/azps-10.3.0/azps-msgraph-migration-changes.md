---
description: This migration guide contains a list of Azure PowerShell changes for the Azure AD to Microsoft Graph migration in Az.Resources 5.1.0.
ms.custom: devx-track-azurepowershell
ms.date: 09/05/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure AD to Microsoft Graph migration changes in Azure PowerShell
---

# Azure AD to Microsoft Graph migration changes in Azure PowerShell

The `Az.Resources` PowerShell module version 5.1.0 of Azure PowerShell introduces changes to
the identity-related cmdlets. The cmdlets that rely on Azure AD Graph are transitioning to Microsoft
Graph. This change is occurring to ensure a smooth transition in light of the
[announcement of the retirement of Azure AD Graph](https://azure.microsoft.com/updates/update-your-apps-to-use-microsoft-graph-before-30-june-2022/).
For more information, see
[Azure AD to Microsoft Graph migration for Azure command line tools](https://techcommunity.microsoft.com/t5/azure-tools/azure-ad-to-microsoft-graph-migration-for-azure-command-line/ba-p/2836666).

The following example installs the latest version of the `Az.Resources` Azure PowerShell module.

```powershell
Install-Module -Name Az.Resources -Repository PSGallery -Scope CurrentUser
```

See the following information for a list of changes.

## Application

### Get-AzAdApplication

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Parameter `IncludeTotalCount` is not supported and has been removed

### New-AzAdApplication

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Parameter `Password` has been removed, customized password is not supported anymore, server
  assigns secret text when creation

### Remove-AzAdApplication

- Input type of parameter `InputObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### Update-AzAdApplication

- Input type of parameter `InputObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `System.Boolean`

### Changes to Application Object

- `ObjectId` has been replaced by `Id`

- `HomePage` has been replaced by `HomepageUrl` in the `Web` element

- `ApplicationId` has been replaced by `AppId`

- `AvailableToOtherTenants` (boolean) has been replaced by `SignInAudience` (string with 4 values:
  'AzureADMyOrg', 'AzureADMultipleOrgs', 'AzureADandPersonalMicrosoftAccount',
  'PersonalMicrosoftAccount')

  - AzureADMultipleOrgs is equivalent to AvailableToOtherTenants:$true

  - AzureAdMyOrg is equivalent to AvailableToOtherTenants:$false or $null

- `ApiPermissions` has been replaced by `RequiredResourceAccess`

- `ReplyUrls` has been replaced by `RedirectUris ` in the `Web` element

- `ObjectType` has been replaced by `OdataType`

## Application Credential

### Get-AzAdAppCredential

- Input type of parameter `ApplicationObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  and `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### New-AzAdAppCredential

- Input type of parameter `ApplicationObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  and `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

- Parameter `Password` has been removed, customized password is not supported anymore, server will
  assign secret text when creation

### Remove-AzAdAppCredential

- Input type of parameter `ApplicationObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### Changes to App Credential Object

#### Password Credential
- `Password` has been replaced by `SecretText`

#### Key Credential
- `CertValue` has been Removed

## ServicePrincipal

### Get-AzAdServicePrincipal

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal`
  to `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Parameter `IncludeTotalCount` is not supported and has been removed.

### New-AzAdServicePrincipal

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal`
  to `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Parameter set `ApplicationWithoutCredentialParameterSet`,
  `ApplicationWithPasswordPlainParameterSet`, `DisplayNameWithoutCredentialParameterSet`,
  `DisplayNameWithPasswordPlainParameterSet` have been removed because those original parameter sets
  were not functioning.

- Role `contributor` is not assigned as default when parameter `-Role` is not provided due to
  security consideration.

- Parameter `SkipAssignment` has been removed.

### Remove-AzAdServicePrincipal

- Input type of parameter `ApplicationObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Input type of parameter `InputObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### Update-AzAdServicePrincipal

- Input type of parameter `InputObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal`
  to `System.Boolean`

### Changes to Service Principal Object

- `ApplicationId` has been replaced by `AppId`

- `ObjectType` has been replaced by `OdataType`

## ServicePrincipal Credential

### Get-AzAdSpCredential

- Input type of parameter `ServicePrincipalObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  and `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### New-AzAdSpCredential

- Input type of parameter `ServicePrincipalObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  and `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### Remove-AzAdSpCredential

- Input type of parameter `ServicePrincipalObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### Changes to ServicePrincipal Credential Object

#### Password Credential
- `Password` has been replaced by `SecretText`

#### Key Credential
- `CertValue` has been Removed

## User

### Get-AzAdUser

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Parameter `IncludeTotalCount` is not supported and has been removed

### New-AzAdUser

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### Remove-AzAdUser

- Input type of parameter `InputObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### Update-AzAdUser

- Input type of parameter `InputObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` to
  `System.Boolean`

### Changes to User Object

- `ObjectType` has been replaced by `OdataType`

- `ImmutableId` has been replaced by `OnpremisesImmutableId`

## Group

### Get-AzAdGroup

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

- Parameter `IncludeTotalCount` is not supported and has been removed

### New-AzAdGroup

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### Remove-AzAdGroup

- Input type of parameter `InputObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### Changes of Group Object

- `ObjectType` has been replaced by `OdataType`

## Group member

### Get-AzAdGroupMember

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADObject` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDirectoryObject`

- Parameter `IncludeTotalCount` was removed

- Input type of parameter `GroupObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

[!INCLUDE [get-azadgroupmember-no-serviceprincipal-banner](../../includes/get-azadgroupmember-no-serviceprincipal-banner.md)]

### Add-AzAdGroupMember

- Input type of parameter `GroupObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### Remove-AzAdGroupMember

- Input type of parameter `GroupObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`
