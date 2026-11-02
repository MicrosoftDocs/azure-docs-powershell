---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/27/2026
PlatyPS schema version: 2024-05-01
title: Stop-AzResourceGroupDeployment
---

# Stop-AzResourceGroupDeployment

## SYNOPSIS

Cancel a currently running resource group deployment.

## SYNTAX

### __AllParameterSets

```
Stop-AzResourceGroupDeployment [-ResourceGroupName] <string> [-Name] <string>
 [-SubscriptionId <string>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Cancels a running Azure Resource Manager deployment scoped to a resource group. A deployment can only be cancelled while its provisioning state is `Accepted` or `Running`; once cancelled the state becomes `Canceled` and the resource group is left partially deployed, so any resources the deployment already created remain and must be cleaned up separately. Cancelling a deployment that has already reached a terminal state fails with `DeploymentCannotBeCancelled`. The cmdlet emits nothing on success. The subscription defaults to the active profile's subscription unless `-SubscriptionId` is supplied.

## EXAMPLES

### Cancel a running deployment

Stop the in-flight deployment named `infra-prod-2026-06-18` in resource group `myrg`.

```powershell
Stop-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18
```

### Cancel a running deployment in a specific subscription

Target a subscription other than the active profile's.

```powershell
Stop-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18 -SubscriptionId 00000000-0000-0000-0000-000000000000
```

### Cancel a deployment unattended

`Stop-AzResourceGroupDeployment` supports `ShouldProcess` with a `Medium` confirm impact, so it does not prompt under the default `$ConfirmPreference` of `High`. Pass `-Confirm:$false` to keep it silent even where `$ConfirmPreference` has been lowered, and inspect the resulting state afterwards.

```powershell
Stop-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18 -Confirm:$false
(Get-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18).Properties.ProvisioningState
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

### -Name

The name of the deployment to cancel.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: (All)
  Position: 1
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Use the named profile for this command, overriding the active profile.

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

### -ResourceGroupName

The name of the resource group that contains the deployment.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubscriptionId

Azure subscription id. Defaults to the active profile's subscription.

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

### System.String

You can pipe the **ResourceGroupName** and **Name** values to this cmdlet by property name, for example the output of `Get-AzResourceGroupDeployment`.

## OUTPUTS

### System.Void

Nothing is emitted on success. Azure Resource Manager answers the cancel request with HTTP 204 No Content, so a silent return and a zero exit status mean the deployment was cancelled. Failures surface as terminating errors.

## NOTES

Only a deployment whose provisioning state is `Accepted` or `Running` can be cancelled. Cancelling stops the deployment where it stands and leaves the resource group partially deployed; resources already created are not rolled back. Use `Get-AzResourceGroupDeployment` to confirm the deployment reached the `Canceled` state.

## RELATED LINKS


- [Get-AzResourceGroupDeployment](Get-AzResourceGroupDeployment.md)
- [New-AzResourceGroupDeployment](New-AzResourceGroupDeployment.md)
- [Remove-AzResourceGroupDeployment](Remove-AzResourceGroupDeployment.md)
