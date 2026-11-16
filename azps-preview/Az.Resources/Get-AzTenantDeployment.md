---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 11/04/2026
PlatyPS schema version: 2024-05-01
title: Get-AzTenantDeployment
---

# Get-AzTenantDeployment

## SYNOPSIS

Get deployments at tenant scope.

## SYNTAX

### GetByDeploymentName (Default)

```
Get-AzTenantDeployment [[-Name] <string>] [-Profile <string>] [<CommonParameters>]
```

### ListByFilter

```
Get-AzTenantDeployment -Filter <string> [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

Without `-Name`, lists every deployment at tenant scope, following all pages of results. With
`-Name`, gets that deployment and fails if it does not exist. With `-Filter`, lists the
deployments that match an OData filter, for example by provisioning state.

## EXAMPLES

### List all tenant deployments

```powershell
Get-AzTenantDeployment
```

### Get a deployment by name

```powershell
Get-AzTenantDeployment -Name tenant-infra
```

### List succeeded deployments

```powershell
Get-AzTenantDeployment -Filter "provisioningState eq 'Succeeded'"
```

## PARAMETERS

### -Filter

An OData filter sent to the tenant deployment list API, for example "provisioningState eq 'Succeeded'".

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ListByFilter
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

The name of the deployment. Lists every tenant deployment when omitted.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: GetByDeploymentName
  Position: 0
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

This cmdlet does not accept pipeline input.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended

One `DeploymentExtended` object per deployment.

## NOTES

Differences from Az.Resources: the cmdlet returns the `DeploymentExtended` model instead of `PSDeployment`. `-Id` and `-Pre` are not supported. `-Filter` is an Azclips addition that matches `az deployment tenant list --filter`.

## RELATED LINKS

- [New-AzTenantDeployment](New-AzTenantDeployment.md)
- [Stop-AzTenantDeployment](Stop-AzTenantDeployment.md)
- [Remove-AzTenantDeployment](Remove-AzTenantDeployment.md)
