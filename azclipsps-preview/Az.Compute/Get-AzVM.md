---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Compute.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Compute
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Get-AzVM
---

# Get-AzVM

## SYNOPSIS

Show details for a virtual machine.

## SYNTAX

### List (Default)

```
Get-AzVM -SubscriptionId <string> -ResourceGroupName <string> [-Profile <string>]
 [<CommonParameters>]
```

### Get

```
Get-AzVM -SubscriptionId <string> -ResourceGroupName <string> -Name <string> [-Profile <string>]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Retrieves the properties of a single virtual machine identified by name within the specified resource group and subscription.

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

## PARAMETERS

### -Name

The name of the virtual machine.

```yaml
Type: System.String
DefaultValue: ""
SupportsWildcards: false
Aliases: []
ParameterSets:
    - Name: Get
      Position: Named
      IsRequired: true
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -ResourceGroupName

The resource group name.

```yaml
Type: System.String
DefaultValue: ""
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
      IsRequired: true
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### -SubscriptionId

Azure Subscription Id.

```yaml
Type: System.String
DefaultValue: ""
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
      IsRequired: true
      ValueFromPipeline: false
      ValueFromPipelineByPropertyName: false
      ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ""
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Compute.Models.VirtualMachine

One `VirtualMachine` object per matching VM — a single result when `-Name` is supplied (Get mode), an array of results otherwise (List mode). Each includes the ARM resource ID, provisioning state, VM size, and network configuration.

## NOTES

Generated help for compute.

## RELATED LINKS

- [Online Version]()
