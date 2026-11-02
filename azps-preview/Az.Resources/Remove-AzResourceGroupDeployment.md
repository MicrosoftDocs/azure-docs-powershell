---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/27/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzResourceGroupDeployment
---

# Remove-AzResourceGroupDeployment

## SYNOPSIS

Delete a resource group deployment from the deployment history.

## SYNTAX

### RemoveByResourceGroupName (Default)

```
Remove-AzResourceGroupDeployment [-ResourceGroupName] <string> [-Name] <string>
 [-SubscriptionId <string>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByResourceGroupDeploymentId

```
Remove-AzResourceGroupDeployment -Id <string> [-SubscriptionId <string>] [-Profile <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Deletes an Azure Resource Manager deployment scoped to a resource group. This removes the deployment record and its associated deployment operations from the deployment history; it does **not** delete the resources the deployment created, and it leaves the resource group itself untouched.

A deployment that is currently running cannot be deleted -- cancel it with `Stop-AzResourceGroupDeployment` first, or wait for it to reach a terminal state. The delete is a long-running operation and the cmdlet waits for it to finish.

Deleting a deployment name that does not exist succeeds silently, because ARM answers the same `204 No Content` whether or not the deployment was there. The cmdlet emits nothing on success.

The deployment can be identified either by `-ResourceGroupName` and `-Name` or by its fully qualified `-Id`. When `-Id` is used, the subscription is always taken from the id and `-SubscriptionId` is ignored; otherwise the subscription defaults to the active profile's.

## EXAMPLES

### Delete a deployment from the history

Remove the record of the deployment named `infra-prod-2026-06-18` in resource group `myrg`.

```powershell
Remove-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18
```

### Delete a deployment using positional arguments

`-ResourceGroupName` and `-Name` are positional, so the parameter names can be omitted.

```powershell
Remove-AzResourceGroupDeployment myrg infra-prod-2026-06-18
```

### Delete a deployment by resource id

Target the deployment by its fully qualified resource id. The subscription is read from the id.

```powershell
Remove-AzResourceGroupDeployment -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Resources/deployments/infra-prod-2026-06-18
```

### Delete a deployment in a specific subscription without being prompted

`Remove-AzResourceGroupDeployment` supports `ShouldProcess` with a `Medium` confirm impact, so it does not prompt under the default `$ConfirmPreference` of `High`. Pass `-Confirm` to request a prompt, or `-Confirm:$false` to stay unattended even where `$ConfirmPreference` has been lowered.

```powershell
Remove-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18 -SubscriptionId 00000000-0000-0000-0000-000000000000 -Confirm:$false
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

The fully qualified resource id of the deployment, in the form `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}`. The subscription, resource group and deployment name are all read from the id; `-SubscriptionId` is ignored when `-Id` is used. A malformed id fails before any request is sent.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentId
- ResourceId
ParameterSets:
- Name: RemoveByResourceGroupDeploymentId
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

The name of the deployment to delete. Accepts the legacy alias `-DeploymentName`, and can be supplied positionally as the second argument.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: RemoveByResourceGroupName
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

The name of the resource group that contains the deployment. Can be supplied positionally as the first argument.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: RemoveByResourceGroupName
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

Azure subscription id. Defaults to the active profile's subscription. Ignored when `-Id` is used; the subscription embedded in the id always wins.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: RemoveByResourceGroupName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: RemoveByResourceGroupDeploymentId
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

Nothing is emitted on success. Azure Resource Manager answers the delete request with HTTP 204 No Content, so a silent return and a zero exit status mean the deployment record was deleted. Failures surface as terminating errors.

## NOTES

Deleting a deployment removes only the deployment record from the history of the resource group. Resources created by that deployment are left untouched.

A deployment that is still running cannot be deleted; Azure Resource Manager rejects the request. Cancel it first with `Stop-AzResourceGroupDeployment`, then delete it.

Deleting a name that does not exist is not an error. Azure Resource Manager answers 204 No Content for an absent deployment, so the cmdlet returns silently. This differs from `Remove-AzResourceGroupDeployment` in Az.Resources, which performs an existence check first and throws.

The delete is a long-running operation. The cmdlet polls until Azure Resource Manager reports the operation complete before returning.

## RELATED LINKS


- [Get-AzResourceGroupDeployment](Get-AzResourceGroupDeployment.md)
- [New-AzResourceGroupDeployment](New-AzResourceGroupDeployment.md)
- [Stop-AzResourceGroupDeployment](Stop-AzResourceGroupDeployment.md)
