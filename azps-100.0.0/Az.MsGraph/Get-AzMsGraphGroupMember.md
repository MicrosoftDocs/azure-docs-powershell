---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.MsGraph.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.MsGraph
ms.date: 09/01/2026
PlatyPS schema version: 2024-05-01
title: Get-AzMsGraphGroupMember
---

# Get-AzMsGraphGroupMember

## SYNOPSIS

Lists the members of a Microsoft Entra group.

## SYNTAX

### ObjectId (Default)

```
Get-AzMsGraphGroupMember -GroupObjectId <string> [-Filter <string>] [-Select <string[]>]
 [-Expand <string[]>] [-Orderby <string[]>] [-Search <string>] [-ConsistencyLevel <string>]
 [<CommonParameters>]
```

### DisplayName

```
Get-AzMsGraphGroupMember -GroupDisplayName <string> [-Filter <string>] [-Select <string[]>]
 [-Expand <string[]>] [-Orderby <string[]>] [-Search <string>] [-ConsistencyLevel <string>]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

List every user, group, service principal, or device that is a direct member of the specified group. Identify the target group by object ID (`-GroupObjectId`) or by exact display name (`-GroupDisplayName`). Use `-Filter`, `-Search`, and `-Orderby` for custom queries on the returned members.

## EXAMPLES

### Example 1: List members by group object ID

```powershell
Get-AzMsGraphGroupMember -GroupObjectId 11111111-2222-3333-4444-555555555555
```

### Example 2: List members by group display name

```powershell
Get-AzMsGraphGroupMember -GroupDisplayName 'Sales Team'
```

### Example 3: List members whose display name starts with a prefix

```powershell
Get-AzMsGraphGroupMember -GroupObjectId 11111111-2222-3333-4444-555555555555 -Filter "startswith(displayName,'Ada')"
```

## PARAMETERS

### -ConsistencyLevel

Set to `eventual` to enable advanced query features such as `$search`, `$count`, or `$orderby` on non-indexed properties.

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

### -Expand

Related properties to include in the response.

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

### -Filter

OData `$filter` expression.

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

### -GroupDisplayName

The exact display name of the target group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: DisplayName
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -GroupObjectId

The object ID of the group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Id
- ObjectId
ParameterSets:
- Name: ObjectId
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Orderby

OData `$orderby` values.

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

### -Search

OData `$search` expression. Requires `-ConsistencyLevel eventual`.

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

### -Select

Properties to return.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

The directory objects (users, groups, service principals, or devices) that are members of the group.

## NOTES

## RELATED LINKS

