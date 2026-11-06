---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/19/2026
PlatyPS schema version: 2024-05-01
title: Get-AzManagementGroupDeployment
---

# Get-AzManagementGroupDeployment

## SYNOPSIS

Gets management-group deployments.

## SYNTAX

### GetByDeploymentName (Default)

```
Get-AzManagementGroupDeployment [-ManagementGroupId] <string> [[-Name] <string>] [-Profile <string>]
 [<CommonParameters>]
```

### GetByDeploymentId

```
Get-AzManagementGroupDeployment -Id <string> [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Lists deployments when only `-ManagementGroupId` is supplied. Gets one deployment when
`-ManagementGroupId` and `-Name`, or a full deployment `-Id`, are supplied.
List results are written as individual deployment objects.

## EXAMPLES

### Example 1

Lists all deployments recorded at a management group.

```powershell
Get-AzManagementGroupDeployment -ManagementGroupId myManagementGroup
```

### Example 2

Gets one deployment by management group and name.

```powershell
Get-AzManagementGroupDeployment -ManagementGroupId myManagementGroup -Name myDeployment
```

### Example 3

Gets one deployment by full resource ID.

```powershell
$id = '/providers/Microsoft.Management/managementGroups/myManagementGroup/providers/Microsoft.Resources/deployments/myDeployment'
Get-AzManagementGroupDeployment -Id $id
```

## PARAMETERS

### -Id

The full management-group deployment resource ID, for example
`/providers/Microsoft.Management/managementGroups/myManagementGroup/providers/Microsoft.Resources/deployments/myDeployment`.
Use this instead of `-ManagementGroupId` and `-Name`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentId
- ResourceId
ParameterSets:
- Name: GetByDeploymentId
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ManagementGroupId

The management group ID.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: GetByDeploymentName
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

The deployment name. Omit it to list deployments.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: GetByDeploymentName
  Position: 1
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

The AzClips profile to use instead of the active profile.

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

Returns one or more management-group deployment objects.

## NOTES

The full ID form must identify a `Microsoft.Resources/deployments` resource beneath a
`Microsoft.Management/managementGroups` scope.
`-Id` also accepts the aliases `-DeploymentId` and `-ResourceId`; `-Name` accepts `-DeploymentName`.
The legacy `-Pre` switch is not supported.

## RELATED LINKS


- [Azure Resource Manager deployments](https://learn.microsoft.com/azure/azure-resource-manager/templates/deploy-to-management-group)
