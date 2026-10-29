---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Compute.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Compute
ms.date: 09/28/2026
PlatyPS schema version: 2024-05-01
title: Stop-AzVM
---

# Stop-AzVM

## SYNOPSIS

Stop a running virtual machine.

## SYNTAX

### ResourceGroupNameParameterSet (Default)

```
Stop-AzVM [-ResourceGroupName] <string> [-Name] <string> [-SubscriptionId <string>]
 [-StayProvisioned] [-SkipShutdown] [-ForceDeallocate] [-Force] [-Profile <string>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ResourceGroupHibernateParameterSet

```
Stop-AzVM [-ResourceGroupName] <string> [-Name] <string> [-SubscriptionId <string>] [-Hibernate]
 [-Force] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdParameterSet

```
Stop-AzVM [-Id] <string> [-SubscriptionId <string>] [-StayProvisioned] [-SkipShutdown]
 [-ForceDeallocate] [-Force] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdHibernateParameterSet

```
Stop-AzVM [-Id] <string> [-SubscriptionId <string>] [-Hibernate] [-Force] [-Profile <string>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Stops a running virtual machine.
By default the virtual machine is deallocated, which releases its compute resources so they are no longer billed.
Use `-StayProvisioned` to power the virtual machine off while keeping it allocated; it continues to be billed but retains its provisioned compute resources.
Target a single VM either by `-Name` and `-ResourceGroupName`, or by its full resource id with `-Id`.
When `-Id` is used it supplies the subscription, resource group, and VM name, so `-SubscriptionId` is ignored.
The cmdlet prompts for confirmation unless `-Force` is supplied, waits for the long-running operation to finish, and does not emit an object on success.

## EXAMPLES

### Stop and deallocate a VM by name

Deallocate the virtual machine `myvm` in resource group `myrg` so it stops accruing compute charges.

```powershell
Stop-AzVM -ResourceGroupName myrg -Name myvm -Force
```

### Power off a VM but keep it provisioned

Power the virtual machine off without releasing its compute resources. The VM continues to be billed.

```powershell
Stop-AzVM -ResourceGroupName myrg -Name myvm -StayProvisioned -Force
```

### Power off a VM without a graceful shutdown

Skip the guest shutdown sequence and power the virtual machine off immediately.

```powershell
Stop-AzVM -ResourceGroupName myrg -Name myvm -StayProvisioned -SkipShutdown -Force
```

### Hibernate a VM while deallocating it

Hibernate the virtual machine as part of the deallocate so its memory state is preserved.

```powershell
Stop-AzVM -ResourceGroupName myrg -Name myvm -Hibernate -Force
```

### Stop a VM by resource id

Deallocate a virtual machine addressed by its full ARM resource id.

```powershell
Stop-AzVM -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Compute/virtualMachines/myvm -Force
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

### -Force

To force the stopping.

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

### -ForceDeallocate

Optional parameter to force deallocate a virtual machine during stop operations. Cannot be used with -StayProvisioned, -SkipShutdown, or -Hibernate.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupNameParameterSet
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: IdParameterSet
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Hibernate

Optional parameter to hibernate a virtual machine.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupHibernateParameterSet
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: IdHibernateParameterSet
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
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: IdHibernateParameterSet
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

The name of the virtual machine.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupNameParameterSet
  Position: 1
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ResourceGroupHibernateParameterSet
  Position: 1
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

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

### -ResourceGroupName

The resource group name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupNameParameterSet
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ResourceGroupHibernateParameterSet
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SkipShutdown

To request non-graceful VM shutdown when keeping the VM provisioned.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupNameParameterSet
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: IdParameterSet
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -StayProvisioned

To keep the VM provisioned.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroupNameParameterSet
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: IdParameterSet
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
