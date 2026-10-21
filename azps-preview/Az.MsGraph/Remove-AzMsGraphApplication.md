---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.MsGraph.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.MsGraph
ms.date: 09/01/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzMsGraphApplication
---

# Remove-AzMsGraphApplication

## SYNOPSIS

Deletes a Microsoft Graph application registration.

## SYNTAX

### __AllParameterSets

```
Remove-AzMsGraphApplication -Id <string> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Deletes an application registration from Microsoft Graph using the active Azure profile (see `Connect-AzAccount`). The identifier is the application's object ID. Graph performs a soft delete; the application is recoverable for 30 days.

## EXAMPLES

### Example 1: Delete an application by object ID

```powershell
Remove-AzMsGraphApplication -Id 00000000-0000-0000-0000-000000000000
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

The object ID of the application registration to delete.

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

## INPUTS

### None

## OUTPUTS

### System.Void

### System.Object

## NOTES

## RELATED LINKS

