---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.MsGraph.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.MsGraph
ms.date: 09/01/2026
PlatyPS schema version: 2024-05-01
title: Get-AzMsGraphUser
---

# Get-AzMsGraphUser

## SYNOPSIS

Gets Microsoft Entra users.

## SYNTAX

### List (Default)

```
Get-AzMsGraphUser [-Filter <string>] [-Orderby <string[]>] [-Search <string>]
 [-ConsistencyLevel <string>] [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### Mail

```
Get-AzMsGraphUser -Mail <string> [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### DisplayName

```
Get-AzMsGraphUser -DisplayName <string> [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### StartsWith

```
Get-AzMsGraphUser -StartsWith <string> [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### Get

```
Get-AzMsGraphUser -Id <string> [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

### SignedIn

```
Get-AzMsGraphUser -SignedIn [-Select <string[]>] [-Expand <string[]>] [-AppendSelected]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Look up Microsoft Entra users in your tenant. Without parameters, lists users in the signed-in tenant. Use `-Id` to retrieve a single user by object ID or user principal name; `-SignedIn` for the currently signed-in user; `-Mail`, `-DisplayName`, or `-StartsWith` to match by that property; or `-Filter`, `-Orderby`, `-Search` for custom queries.

## EXAMPLES

### Example 1: List all users

```powershell
Get-AzMsGraphUser
```

### Example 2: List users with the specified mail address

```powershell
Get-AzMsGraphUser -Mail ada@contoso.com
```

### Example 3: List users with the specified display name

```powershell
Get-AzMsGraphUser -DisplayName 'Ada Lovelace'
```

### Example 4: List users whose display name starts with a prefix

```powershell
Get-AzMsGraphUser -StartsWith Ada
```

### Example 5: List users with a custom filter expression

```powershell
Get-AzMsGraphUser -Filter "endswith(mail,'@contoso.com')" -ConsistencyLevel eventual
```

### Example 6: Get a user by object ID or user principal name

```powershell
Get-AzMsGraphUser -Id 00000000-0000-0000-0000-000000000000
```

### Example 7: Get the currently signed-in user

```powershell
Get-AzMsGraphUser -SignedIn
```

### Example 8: Return a subset of properties, widened with the defaults

```powershell
Get-AzMsGraphUser -Select 'city','department' -AppendSelected
```

## PARAMETERS

### -AppendSelected

When set with `-Select`, include the default property set (`displayName`, `id`, `deletedDateTime`, `userPrincipalName`, `usageLocation`, `givenName`, `surname`, `accountEnabled`, `mailNickname`, `mail`) alongside the values in `-Select` rather than replacing them.

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
- Name: Mail
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
- Name: StartsWith
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
- Name: SignedIn
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

List users with the specified display name.

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

### -Expand

Related properties to include in the response, for example `memberOf`.

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
- Name: Mail
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
- Name: StartsWith
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
- Name: SignedIn
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

OData `$filter` expression, for example `"accountEnabled eq true"`.

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

### -Id

The object ID or user principal name (UPN) of the user to retrieve.

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

### -Mail

List users with the specified mail address.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Mail
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

OData `$orderby` values, for example `'displayName'` or `'mail desc'`.

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

OData `$search` expression, for example `"displayName:ada"`. Requires `-ConsistencyLevel eventual`.

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
- Name: Mail
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
- Name: StartsWith
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
- Name: SignedIn
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SignedIn

Return the currently signed-in user.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: SignedIn
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -StartsWith

List users whose display name starts with the specified prefix.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: StartsWith
  Position: Named
  IsRequired: true
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

The Microsoft Entra user object or objects returned by the query.

## NOTES

## RELATED LINKS

