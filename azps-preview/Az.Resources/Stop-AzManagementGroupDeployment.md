---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/19/2026
PlatyPS schema version: 2024-05-01
title: Stop-AzManagementGroupDeployment
---

# Stop-AzManagementGroupDeployment

## SYNOPSIS

Cancels a running management-group deployment.

## SYNTAX

### StopByDeploymentName (Default)

```
Stop-AzManagementGroupDeployment [-ManagementGroupId] <string> [-Name] <string> [-PassThru]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StopByDeploymentId

```
Stop-AzManagementGroupDeployment -Id <string> [-PassThru] [-Profile <string>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### StopByInputObject

```
Stop-AzManagementGroupDeployment -InputObject <DeploymentExtended> [-PassThru] [-Profile <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Cancels a deployment in Accepted or Running state. The target can be supplied by management
group and name, full deployment ID, or pipeline input object.
The cmdlet sends the cancellation request directly; Azure Resource Manager checks the deployment state.
Cancellation does not roll back resources already deployed. No deployment object is returned.

## EXAMPLES

### Example 1

Cancels a deployment by management group and name.

```powershell
Stop-AzManagementGroupDeployment -ManagementGroupId myManagementGroup -Name myDeployment -Confirm:$false
```

### Example 2

Cancels a deployment supplied through the pipeline and returns `true` on success.

```powershell
Get-AzManagementGroupDeployment -ManagementGroupId myManagementGroup -Name myDeployment |
    Stop-AzManagementGroupDeployment -PassThru -Confirm:$false
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
- Name: StopByDeploymentId
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
Its `Id` identifies the deployment to cancel. Accepts pipeline input.

```yaml
Type: Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: StopByInputObject
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
- Name: StopByDeploymentName
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
- Name: StopByDeploymentName
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

Writes `true` after the cancellation call returns without a terminating error.
No value is written when `-WhatIf` or a declined confirmation skips cancellation.

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

Shows PowerShell's cancellation action message without sending a cancellation request.
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

No output by default. With `-PassThru`, writes `true` after the cancellation call returns.
No value is written when `-WhatIf` or a declined confirmation skips cancellation.

## NOTES

Completed, failed, or canceled deployments cannot be canceled.
The legacy `-Pre` and `-AsJob` switches are not supported.

## RELATED LINKS


- [Azure Resource Manager deployments](https://learn.microsoft.com/azure/azure-resource-manager/templates/deploy-to-management-group)
