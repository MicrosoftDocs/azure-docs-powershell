---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.ManagedServiceIdentity.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.ManagedServiceIdentity
ms.date: 09/04/2026
PlatyPS schema version: 2024-05-01
title: Get-AzUserAssignedIdentity
---

# Get-AzUserAssignedIdentity

## SYNOPSIS

Gets user-assigned managed identities.

## SYNTAX

### List (Default)

```
Get-AzUserAssignedIdentity [-SubscriptionId <string>] [-ResourceGroupName <string>]
 [-Profile <string>] [<CommonParameters>]
```

### Get

```
Get-AzUserAssignedIdentity -ResourceGroupName <string> -Name <string> [-SubscriptionId <string>]
 [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Gets a user-assigned managed identity by name, lists identities in a resource group, or lists identities in the subscription.

## EXAMPLES

### Example 1: Get a user-assigned managed identity

Get a user-assigned managed identity by resource group and name.

```powershell
Get-AzUserAssignedIdentity -ResourceGroupName myResourceGroup -Name myIdentity
```

### Example 2: List user-assigned managed identities in a resource group

List all user-assigned managed identities in a resource group.

```powershell
Get-AzUserAssignedIdentity -ResourceGroupName myResourceGroup
```

## PARAMETERS

### -Name

Specifies the name of the user-assigned managed identity.

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

Specifies the name of the resource group. When omitted, the cmdlet lists identities in the subscription.

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

### -SubscriptionId

Specifies the Azure subscription ID. If omitted, the active profile subscription is used.

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
