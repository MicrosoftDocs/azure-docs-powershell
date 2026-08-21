---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Login.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Login
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: Disconnect-AzAccount
---

# Disconnect-AzAccount

## SYNOPSIS

Sign out from the current Azure account context.

## SYNTAX

### __AllParameterSets

```
Disconnect-AzAccount [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Sign out from the current Azure account context.

## EXAMPLES

### Sign out of the current account

Clears the persisted Azure account context. Subsequent Azclips cmdlets will require a fresh `Connect-AzAccount` before they can authenticate.

```powershell
Disconnect-AzAccount
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

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.
Runs the command in a mode that only reports what would happen without performing the actions.
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

Generated help for login.

## RELATED LINKS


- [Online Version]()
