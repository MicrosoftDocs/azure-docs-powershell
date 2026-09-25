---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.MsGraph.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.MsGraph
ms.date: 09/01/2026
PlatyPS schema version: 2024-05-01
title: New-AzMsGraphApplication
---

# New-AzMsGraphApplication

## SYNOPSIS

Creates a Microsoft Graph application registration.

## SYNTAX

### __AllParameterSets

```
New-AzMsGraphApplication -DisplayName <string> [-SignInAudience <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Creates a new application registration in Microsoft Graph using the active Azure profile (see `Connect-AzAccount`). Only a display name is required; the created application, including its generated object ID and app ID, is returned.

## EXAMPLES

### Example 1: Create an application registration

```powershell
New-AzMsGraphApplication -DisplayName my-app
```

### Example 2: Create an application for a single-tenant audience

```powershell
New-AzMsGraphApplication -DisplayName my-app -SignInAudience AzureADMyOrg
```

## PARAMETERS

### -DisplayName

The display name of the application registration.

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

### -SignInAudience

The Microsoft account types supported for sign-in, for example AzureADMyOrg, AzureADMultipleOrgs, or AzureADandPersonalMicrosoftAccount.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.MsGraph.Models.Application

### System.Object

## NOTES

## RELATED LINKS

