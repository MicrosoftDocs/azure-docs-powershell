---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 11/04/2026
PlatyPS schema version: 2024-05-01
title: Save-AzTenantDeploymentTemplate
---

# Save-AzTenantDeploymentTemplate

## SYNOPSIS

Save the template used by a tenant-scope deployment to a file.

## SYNTAX

### Default (Default)

```
Save-AzTenantDeploymentTemplate [-DeploymentName] <string> [-Path <string>] [-Force]
 [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

Exports the template used by a tenant deployment and writes it to a JSON file. Without `-Path`,
the file is `<DeploymentName>.json` in the current location. When `-Path` is an existing folder,
the file is written there as `<DeploymentName>.json`; otherwise `-Path` is the file itself and
gains a `.json` extension when it lacks one. An existing file is overwritten only with `-Force`.

## EXAMPLES

### Save a deployment template to the current location

```powershell
Save-AzTenantDeploymentTemplate -DeploymentName tenant-infra
```

### Save a deployment template to a folder, overwriting an existing file

```powershell
Save-AzTenantDeploymentTemplate -DeploymentName tenant-infra -Path .\templates -Force
```

## PARAMETERS

### -DeploymentName

The name of the deployment whose template to save.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Name
ParameterSets:
- Name: (All)
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Force

Overwrite the template file when it already exists.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### -Path

The file or folder to write the template to. A folder receives '<DeploymentName>.json'. Defaults to the current location.

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

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

This cmdlet does not accept pipeline input.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Processors.DeploymentTemplateSaveResult

An object whose `Path` property is the full path of the template file that was written.

## NOTES

Differences from Az.Resources: an existing file without `-Force` raises an error instead of prompting for confirmation, and a response without a template raises an error. `-DeploymentObject`, `-WhatIf`, `-Confirm`, and `-Pre` are not supported.

## RELATED LINKS

- [Get-AzTenantDeployment](Get-AzTenantDeployment.md)
- [New-AzTenantDeployment](New-AzTenantDeployment.md)
