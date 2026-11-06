---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.MsGraph.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.MsGraph
ms.date: 09/01/2026
PlatyPS schema version: 2024-05-01
title: Get-AzMsGraphGroup
---

# Get-AzMsGraphGroup

## SYNOPSIS

Gets Microsoft Entra groups.

## SYNTAX

### List (Default)

```
Get-AzMsGraphGroup [-Filter <string>] [-Orderby <string[]>] [-Search <string>]
 [-ConsistencyLevel <string>] [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### DisplayName

```
Get-AzMsGraphGroup -DisplayName <string> [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### StartsWith

```
Get-AzMsGraphGroup -DisplayNameStartsWith <string> [-Select <string[]>] [-Expand <string[]>]
 [-AppendSelected] [<CommonParameters>]
```

### Get

```
Get-AzMsGraphGroup -ObjectId <string> [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### DisplayNameStartsWith

```
Get-AzMsGraphGroup -DisplayNameStartsWith <string> [-Select <string[]>] [-Expand <string[]>]
 [-AppendSelected] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Look up Microsoft Entra groups in your tenant. Without parameters, lists groups in the signed-in tenant. Use `-ObjectId` to retrieve a single group by object ID; `-DisplayName` or `-DisplayNameStartsWith` to match by display name; or `-Filter`, `-Orderby`, `-Search` for custom queries.

## EXAMPLES

### Example 1: List all groups

```powershell
Get-AzMsGraphGroup
```

### Example 2: List groups with the specified display name

```powershell
Get-AzMsGraphGroup -DisplayName 'Sales Team'
```

### Example 3: List groups whose display name starts with a prefix

```powershell
Get-AzMsGraphGroup -DisplayNameStartsWith Sales
```

### Example 4: List groups with a custom filter expression

```powershell
Get-AzMsGraphGroup -Filter "securityEnabled eq true"
```

### Example 5: Get a group by object ID

```powershell
Get-AzMsGraphGroup -ObjectId 11111111-2222-3333-4444-555555555555
```

### Example 6: Return a subset of properties, widened with the defaults

```powershell
Get-AzMsGraphGroup -Select 'visibility','createdDateTime' -AppendSelected
```

## PARAMETERS

### -AppendSelected

When set with `-Select`, include the default property set (`displayName`, `id`, `deletedDateTime`, `securityEnabled`, `mailEnabled`, `mailNickname`, `description`) alongside the values in `-Select` rather than replacing them.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: DisplayName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: DisplayNameStartsWith
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: Get
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ConsistencyLevel

Set to `eventual` to enable advanced query features such as `$search`, `$count`, or `$orderby` on non-indexed properties.

```yaml
Type: System.String
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
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -DisplayName

List groups with the specified display name.

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

### -DisplayNameStartsWith

List groups whose display name starts with the specified prefix.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- SearchString
ParameterSets:
- Name: DisplayNameStartsWith
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Expand

Related properties to include in the response, for example `members`.

```yaml
Type: System.String[]
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
- Name: DisplayName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: DisplayNameStartsWith
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: Get
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

OData `$filter` expression, for example `"securityEnabled eq true"`.

```yaml
Type: System.String
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
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ObjectId

The object ID of the group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Id
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

### -Orderby

OData `$orderby` values, for example `'displayName'` or `'createdDateTime desc'`.

```yaml
Type: System.String[]
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
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Search

OData `$search` expression, for example `"displayName:contoso"`. Requires `-ConsistencyLevel eventual`.

```yaml
Type: System.String
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
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Select

Properties to return. Combine with `-AppendSelected` to include the default properties as well.

```yaml
Type: System.String[]
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
- Name: DisplayName
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: DisplayNameStartsWith
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: Get
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

The Microsoft Entra group object or objects returned by the query.

## NOTES

## RELATED LINKS

