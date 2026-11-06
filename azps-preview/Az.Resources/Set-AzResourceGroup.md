---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10-09-2026
PlatyPS schema version: 2024-05-01
title: Set-AzResourceGroup
---

# Set-AzResourceGroup

## SYNOPSIS

Replaces the tags on a resource group.

## SYNTAX

### SetByResourceGroupName (Default)

```
Set-AzResourceGroup [-Tag] <hashtable> -Name <string> [-SubscriptionId <string>] [-Profile <string>]
 [<CommonParameters>]
```

### SetByResourceGroupId

```
Set-AzResourceGroup [-Tag] <hashtable> -Id <string> [-SubscriptionId <string>] [-Profile <string>]
 [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

The `Set-AzResourceGroup` cmdlet replaces all tags on an existing resource group.
Specify the resource group by name or by its full ARM resource ID.
Because the supplied tag collection replaces the existing collection, include any tags that you want to retain.
Use an empty hashtable to remove all tags.

## EXAMPLES

### Example 1: Replace resource group tags by name

Replace all tags on a resource group in the active subscription.

```powershell
Set-AzResourceGroup -Name myResourceGroup -Tag @{ Environment = 'Production'; Owner = 'Platform' }
```

### Example 2: Replace resource group tags by resource ID

Identify the resource group with its full ARM resource ID.

```powershell
Set-AzResourceGroup -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup -Tag @{ CostCenter = '1234' }
```

### Example 3: Remove all resource group tags

Pass an empty hashtable to clear the existing tags.

```powershell
Set-AzResourceGroup -Name myResourceGroup -Tag @{}
```

## PARAMETERS

### -Id

Specifies the full ARM resource ID of the resource group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ResourceGroupId
- ResourceId
ParameterSets:
- Name: SetByResourceGroupId
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

Specifies the name of the resource group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ResourceGroupName
ParameterSets:
- Name: SetByResourceGroupName
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Specifies a saved profile to use instead of the active profile.

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

Specifies the Azure subscription ID.
When omitted, the cmdlet uses the active profile's subscription.
The subscription encoded in `Id` takes precedence when the ID parameter set is used.

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

### -Tag

Specifies the complete hashtable of tags to apply to the resource group.
The supplied tags replace all existing tags. Null values are sent as empty strings.

```yaml
Type: System.Collections.Hashtable
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Tags
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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

You can pipe a resource group name to this cmdlet by property name.

### System.Collections.Hashtable

You can pipe a tag hashtable to this cmdlet by property name.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.ResourceGroup

Returns the updated resource group.

## NOTES

This cmdlet replaces tags; it does not merge them with the existing tag collection.

## RELATED LINKS


- [Online Version]()
