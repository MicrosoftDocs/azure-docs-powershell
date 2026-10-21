---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Compute.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Compute
ms.date: 09/28/2026
PlatyPS schema version: 2024-05-01
title: Get-AzVM
---

# Get-AzVM

## SYNOPSIS

Get a virtual machine or list virtual machines.

## SYNTAX

### List (Default)

```
Get-AzVM [-SubscriptionId <string>] [-ResourceGroupName <string>] [-Status] [-UserData]
 [-Profile <string>] [<CommonParameters>]
```

### ListByName

```
Get-AzVM -Name <string> [-SubscriptionId <string>] [-Status] [-UserData] [-Profile <string>]
 [<CommonParameters>]
```

### ListLocation

```
Get-AzVM -Location <string> [-SubscriptionId <string>] [-Status] [-UserData] [-Profile <string>]
 [<CommonParameters>]
```

### Get

```
Get-AzVM -ResourceGroupName <string> -Name <string> [-SubscriptionId <string>] [-UserData]
 [-Profile <string>] [<CommonParameters>]
```

### Id

```
Get-AzVM [-Id] <string> [-SubscriptionId <string>] [-UserData] [-Profile <string>]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Retrieves details of virtual machines in a subscription.
Run without parameters to list every virtual machine in the subscription, or supply `-ResourceGroupName` to list the virtual machines in one resource group.
Supply `-ResourceGroupName` together with `-Name` to retrieve a single virtual machine, or `-Name` alone to find a virtual machine by exact name across the subscription. Wildcards are not supported.
Use `-Location` to list every virtual machine in a location.
Alternatively, address a single virtual machine directly by its ARM resource ID with `-Id`.

## EXAMPLES

### Get details of a specific VM

Retrieve metadata for the virtual machine `myvm` in resource group `myrg`.

```powershell
Get-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000 -ResourceGroupName myrg -Name myvm
```

### List all VMs in a resource group

Return every virtual machine that lives in `myrg`.

```powershell
Get-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000 -ResourceGroupName myrg
```

### List all VMs in the subscription

Return every virtual machine the subscription contains.

```powershell
Get-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000
```

### Find a VM by name across the subscription

Return the virtual machine named `myvm`, whichever resource group it lives in.

```powershell
Get-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000 -Name myvm
```

### List all VMs in a location

```powershell
Get-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000 -Location eastus
```

### List VMs with their power state

Runs one extra request per virtual machine, so it is slow. Details are fetched for at most 100 virtual machines.

```powershell
Get-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000 -ResourceGroupName myrg -Status
```

### Get a VM by resource ID

Retrieve a virtual machine addressed by its ARM resource ID.

```powershell
Get-AzVM -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Compute/virtualMachines/myvm
```

## PARAMETERS

### -Id

The resource ID of the virtual machine. Provide either -Id or -Name and -ResourceGroupName.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Id
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Location

List every virtual machine in this location.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ListLocation
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
- Name: Get
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ListByName
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
- Name: Get
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Status

Retrieve the power state, OS name, OS version, hypervisor generation and maintenance status of each virtual machine. Command will run slow. Details are retrieved for at most 100 virtual machines. Cannot be combined with `-ResourceGroupName` and `-Name` together; use `-Name` alone to get the status of one virtual machine.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ListByName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ListLocation
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
- Name: Get
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ListByName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ListLocation
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: Id
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -UserData

Include the user data properties in the query result.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: Id
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ListByName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ListLocation
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

You can pipe a virtual machine resource ID to this cmdlet by property name.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Compute.Models.VirtualMachine

One `VirtualMachine` object per matching VM. `-ResourceGroupName` with `-Name`, or `-Id`, returns a single VM. The list forms return every match, and `-Name` on its own can match VMs in several resource groups. Each object includes the ARM resource ID, provisioning state, VM size, and network configuration; `-Status` adds the power state, OS name, OS version, hypervisor generation and maintenance status.

## NOTES

Generated help for compute.

## RELATED LINKS


- [Online Version]()
