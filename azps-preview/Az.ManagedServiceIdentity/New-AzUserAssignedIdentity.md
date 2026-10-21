---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.ManagedServiceIdentity.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.ManagedServiceIdentity
ms.date: 09/04/2026
PlatyPS schema version: 2024-05-01
title: New-AzUserAssignedIdentity
---

# New-AzUserAssignedIdentity

## SYNOPSIS

Creates a user-assigned managed identity.

## SYNTAX

### __AllParameterSets

```
New-AzUserAssignedIdentity -ResourceGroupName <string> -Name <string> -Location <string>
 [-SubscriptionId <string>] [-Tag <hashtable>] [-IsolationScope <string>]
 [-ResourceRestriction <string[]>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Creates a user-assigned managed identity in a resource group. You can optionally set tags, assignment resource restrictions, and the identity isolation scope.

## EXAMPLES

### Example 1: Create a user-assigned managed identity

Create a user-assigned managed identity in a resource group.

```powershell
New-AzUserAssignedIdentity -ResourceGroupName myResourceGroup -Name myIdentity -Location eastus
```

### Example 2: Create an identity with tags and assignment restrictions

Create a user-assigned managed identity with tags and restrict assignment to compute resources.

```powershell
New-AzUserAssignedIdentity -ResourceGroupName myResourceGroup -Name myIdentity -Location eastus -Tag @{ env = "test" } -ResourceRestriction Microsoft.Compute -IsolationScope Regional
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

### -IsolationScope

Specifies the identity isolation scope. Valid values are None and Regional.

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

### -Location

Specifies the Azure region where the identity is created.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
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

Specifies the name of the user-assigned managed identity.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
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

Specifies the Azclips profile to use for authentication and defaults.

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

Specifies the name of the resource group that contains the identity.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ResourceRestriction

Specifies the resource provider namespaces that this identity can be assigned to.

```yaml
Type: System.String[]
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

Specifies the Azure subscription ID. If omitted, the active profile subscription is used.

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

Specifies resource tags to apply to the identity.

```yaml
Type: System.Collections.Hashtable
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

### Microsoft.Azure.Azclips.Extensions.ManagedServiceIdentity.Models.UserAssignedIdentity

Microsoft.Azure.Azclips.Extensions.ManagedServiceIdentity.Models.UserAssignedIdentity

## NOTES

None.

## RELATED LINKS

https://learn.microsoft.com/azure/active-directory/managed-identities-azure-resources/overview
