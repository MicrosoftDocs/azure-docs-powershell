---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/09/2026
PlatyPS schema version: 2024-05-01
title: Stop-AzSubDeployment
---

# Stop-AzSubDeployment

## SYNOPSIS

Cancel a currently running subscription-scope deployment.

## SYNTAX

### StopByDeploymentName (Default)

```
Stop-AzSubDeployment [-Name] <string> [-SubscriptionId <string>] [-PassThru] [-Profile <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StopByInputObject

```
Stop-AzSubDeployment -InputObject <DeploymentExtended> [-PassThru] [-Profile <string>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has the following aliases,
  Stop-AzSubscriptionDeployment

## DESCRIPTION

Cancels a running Azure Resource Manager deployment scoped to a subscription. A deployment can only be cancelled while its provisioning state is `Accepted` or `Running`; once cancelled the state becomes `Canceled`, and any resources the deployment already created remain. Cancelling a deployment that has already reached a terminal state fails. Identify the deployment by `-Name`, or by piping a deployment object from `Get-AzSubDeployment`. The cmdlet emits nothing on success unless `-PassThru` is specified.

## EXAMPLES

### Cancel a running deployment

Stop the in-flight deployment named `sub-infra-2026-06-18`.

```powershell
Stop-AzSubDeployment -Name sub-infra-2026-06-18
```

### Cancel a deployment in a specific subscription without being prompted

```powershell
Stop-AzSubDeployment -Name sub-infra-2026-06-18 -SubscriptionId 00000000-0000-0000-0000-000000000000 -Confirm:$false
```

### Cancel a deployment from the pipeline

```powershell
Get-AzSubDeployment -Name sub-infra-2026-06-18 | Stop-AzSubDeployment -PassThru
```

`-PassThru` writes `True` once the cancellation succeeds.

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
Its `Id` identifies the subscription and deployment to cancel. Accepts pipeline input.

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

### -Name

The name of the deployment to cancel.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
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
- Name: StopByDeploymentName
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

No output by default. With `-PassThru`, writes `true` after the cancellation call returns.
Failures surface as terminating errors.

## NOTES

Cancelling does not roll back resources the deployment already created. Use `Get-AzSubDeployment` to confirm the deployment reached the `Canceled` state. The legacy Az.Resources name `Stop-AzSubscriptionDeployment` is accepted as an alias.

## RELATED LINKS

- [Get-AzSubDeployment](./Get-AzSubDeployment.md)
- [New-AzSubDeployment](./New-AzSubDeployment.md)
- [Remove-AzSubDeployment](./Remove-AzSubDeployment.md)
