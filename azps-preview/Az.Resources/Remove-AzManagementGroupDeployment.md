---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/19/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzManagementGroupDeployment
---

# Remove-AzManagementGroupDeployment

## SYNOPSIS

Removes a management-group deployment from deployment history.

## SYNTAX

### RemoveByDeploymentName (Default)

```
Remove-AzManagementGroupDeployment [-ManagementGroupId] <string> [-Name] <string> [-PassThru]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByDeploymentId

```
Remove-AzManagementGroupDeployment -Id <string> [-PassThru] [-Profile <string>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### RemoveByInputObject

```
Remove-AzManagementGroupDeployment -InputObject <DeploymentExtended> [-PassThru]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Deletes deployment history and associated deployment operations. The target can be supplied
by management group and name, full deployment ID, or pipeline input object.
The cmdlet sends the delete request without checking existence first. Removing a deployment
that does not exist succeeds. The cmdlet returns no output by default, or `true` with `-PassThru`.
Deleting deployment history does not delete the deployed resources.

## EXAMPLES

### Example 1

Removes deployment history by management group and name.

```powershell
Remove-AzManagementGroupDeployment -ManagementGroupId myManagementGroup -Name myDeployment -Confirm:$false
```

### Example 2

Removes deployment history supplied through the pipeline and returns `true` on success.

```powershell
Get-AzManagementGroupDeployment -ManagementGroupId myManagementGroup -Name myDeployment |
    Remove-AzManagementGroupDeployment -PassThru -Confirm:$false
```

## PARAMETERS

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- cf
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
- Name: RemoveByDeploymentId
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -InputObject

A deployment object returned by `Get-AzManagementGroupDeployment`.
Its `Id` identifies the deployment history to remove. Accepts pipeline input.

```yaml
Type: Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: RemoveByInputObject
  Position: Named
  IsRequired: true
  ValueFromPipeline: true
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
- Name: RemoveByDeploymentName
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

The deployment name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: RemoveByDeploymentName
  Position: 1
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -PassThru

Writes `true` after the delete call returns without a terminating error, including when the
deployment did not exist.
No value is written when `-WhatIf` or a declined confirmation skips deletion.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### -WhatIf

Shows PowerShell's deletion action message without sending a delete request.
No `-PassThru` value is written.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- wi
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

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended

Accepts a management-group deployment object from the pipeline.

## OUTPUTS

### System.Boolean

With `-PassThru`, writes `true` after the delete call when deletion is not skipped.
No output by default.

## NOTES

Removing deployment history does not delete resources created by the deployment.
The legacy `-Pre` and `-AsJob` switches are not supported.

## RELATED LINKS


- [Azure Resource Manager deployments](https://learn.microsoft.com/azure/azure-resource-manager/templates/deploy-to-management-group)
