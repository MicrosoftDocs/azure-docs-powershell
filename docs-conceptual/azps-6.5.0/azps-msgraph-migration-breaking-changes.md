---
title: Azure AD to Microsoft Graph migration breaking changes in Azure PowerShell
description: This migration guide contains a list of Azure PowerShell breaking changes for the Azure AD to Microsoft Graph migration in the Az version 7.0.0 release.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/01/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Azure AD to Microsoft Graph migration breaking changes in Azure PowerShell

With the release of Az PowerShell module version 7.x, the identity-related cmdlets that rely on
Azure AD Graph are transitioning to Microsoft Graph. This breaking change is occurring because of
the [announcement of the retirement of Azure AD Graph](/updates/update-your-apps-to-use-microsoft-graph-before-30-june-2022/).
Microsoft Graph provides all the functionality of Azure AD Graph along with new functionality.

The following information contains a detailed list of the breaking changes for the cmdlets in the Az
PowerShell module.

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

## User

### Get-AzAdUser

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Parameter `IncludeTotalCount` is not supported and has been removed

### New-AzAdUser

- Output type has been changed from `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Parameter `ImmutableId` is not supported and has been removed (It is a bug in current preview
  version. It should be added and equivalent to `OnPremisesImmutableId`)

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

### Add-AzAdGroupMember

- Input type of parameter `GroupObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### Remove-AzAdGroupMember

- Input type of parameter `GroupObject` has been changed from
  `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` to
  `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

## Differences between output from AAD and MSGraph

### PSADApplication vs IMicrosoftGraphApplication

- ObjectId -> Id

- $app.HomePage -> $app.Web.HomepageUrl

- ApplicationId -> AppId

- AvailableToOtherTenants ->  SignInAudience

  - SignInAudience now have 4 values: 'AzureADMyOrg', 'AzureADMultipleOrgs',
    'AzureADandPersonalMicrosoftAccount', 'PersonalMicrosoftAccount'

  - AvailableToOtherTenants:$true -> AzureADMultipleOrgs'AD

  - AvailableToOtherTenants:$false or $null -> AzureAdMyOrg

- ApiPermissions -> RequiredResourceAccess

- $app.ReplyUrls -> $app.Web.RedirectUris

- ObjectType -> OdataType

For more information, see
[Azure AD to Microsoft Graph migration for Azure command line tools](https://techcommunity.microsoft.com/t5/azure-tools/azure-ad-to-microsoft-graph-migration-for-azure-command-line/ba-p/2836666).
