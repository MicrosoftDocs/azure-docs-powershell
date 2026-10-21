---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Compute.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Compute
ms.date: 09/28/2026
PlatyPS schema version: 2024-05-01
title: Start-AzVM
---

# Start-AzVM

## SYNOPSIS

Start a stopped virtual machine.

## SYNTAX

### ResourceGroupNameParameterSet (Default)

```
Start-AzVM -Name <string> -ResourceGroupName <string> [-SubscriptionId <string>] [-Profile <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdParameterSet

```
Start-AzVM -Id <string> [-SubscriptionId <string>] [-Profile <string>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Powers on a stopped or deallocated virtual machine.
Target a single VM either by `-Name` and `-ResourceGroupName`, or by its full resource id with `-Id`.
When `-Id` is used it supplies the subscription, resource group, and VM name, so `-SubscriptionId` is ignored.
The cmdlet waits for the long-running start operation to finish and does not emit an object on success.

## EXAMPLES

### Start a VM by name

Start the virtual machine `myvm` in resource group `myrg`.

```powershell
Start-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000 -Name myvm -ResourceGroupName myrg
```

### Start a VM by resource id

Start a virtual machine addressed by its full ARM resource id.

```powershell
Start-AzVM -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Compute/virtualMachines/myvm
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

The resource ID of the virtual machine. Use instead of -Name and -ResourceGroupName.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: IdParameterSet
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

The name of the virtual machine.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupNameParameterSet
  Position: Named
  IsRequired: true
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

### -ResourceGroupName

The resource group name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupNameParameterSet
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubscriptionId

Azure Subscription Id. Defaults to the active profile's subscription.

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

## OUTPUTS

### System.Void

This cmdlet does not emit an object on the pipeline; it only writes progress and status messages via the Information and Verbose streams.

## NOTES

Generated help for compute.

## RELATED LINKS


- [Online Version]()
