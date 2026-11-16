---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/09/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzSubDeployment
---

# Remove-AzSubDeployment

## SYNOPSIS

Delete a subscription-scope deployment from the deployment history.

## SYNTAX

### RemoveByDeploymentName (Default)

```
Remove-AzSubDeployment [-Name] <string> [-SubscriptionId <string>] [-PassThru] [-Profile <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByInputObject

```
Remove-AzSubDeployment -InputObject <DeploymentExtended> [-PassThru] [-Profile <string>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has the following aliases,
  Remove-AzSubscriptionDeployment

## DESCRIPTION

Deletes an Azure Resource Manager deployment scoped to a subscription. This removes the deployment record and its operations from the deployment history; it does **not** delete the resources the deployment created.

A deployment that is currently running cannot be deleted -- cancel it with `Stop-AzSubDeployment` first. The delete is a long-running operation and the cmdlet waits for it to finish. Identify the deployment by `-Name`, or by piping a deployment object from `Get-AzSubDeployment`. The cmdlet emits nothing on success unless `-PassThru` is specified.

## EXAMPLES

### Delete a deployment from the history

Remove the record of the deployment named `sub-infra-2026-06-18`.

```powershell
Remove-AzSubDeployment -Name sub-infra-2026-06-18
```

### Delete a deployment in a specific subscription without being prompted

```powershell
Remove-AzSubDeployment -Name sub-infra-2026-06-18 -SubscriptionId 00000000-0000-0000-0000-000000000000 -Confirm:$false
```

### Delete deployments from the pipeline

```powershell
Get-AzSubDeployment -Name sub-infra-2026-06-18 | Remove-AzSubDeployment -PassThru
```

`-PassThru` writes `True` once the delete completes.

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

### -InputObject

A deployment object returned by `Get-AzSubDeployment`.
Its `Id` identifies the subscription and deployment to delete. Accepts pipeline input.

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

### -Name

The name of the deployment to delete from the subscription's deployment history.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
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

### -PassThru

Writes `true` after the delete completes without a terminating error.
No value is written when `-WhatIf` or a declined confirmation skips the delete.

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

### -SubscriptionId

The Azure subscription that owns the deployment. Defaults to the active profile's subscription when omitted.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: RemoveByDeploymentName
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

Runs the command in a mode that only reports what would happen without performing the actions.

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

Accepts a subscription deployment object from the pipeline, for example the output of `Get-AzSubDeployment`.

## OUTPUTS

### System.Boolean

No output by default. With `-PassThru`, writes `true` after the delete completes.
Failures surface as terminating errors.

## NOTES

Deleting a deployment removes only the deployment record. Resources created by that deployment are left untouched. The legacy Az.Resources name `Remove-AzSubscriptionDeployment` is accepted as an alias.

## RELATED LINKS

- [Get-AzSubDeployment](./Get-AzSubDeployment.md)
- [New-AzSubDeployment](./New-AzSubDeployment.md)
- [Stop-AzSubDeployment](./Stop-AzSubDeployment.md)
