---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/09/2026
PlatyPS schema version: 2024-05-01
title: Save-AzSubDeploymentTemplate
---

# Save-AzSubDeploymentTemplate

## SYNOPSIS

Save the template used for a subscription-scope deployment to a file.

## SYNTAX

### SaveByDeploymentName (Default)

```
Save-AzSubDeploymentTemplate -Name <string> [-SubscriptionId <string>] [-Path <string>] [-Force]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SaveByInputObject

```
Save-AzSubDeploymentTemplate -InputObject <DeploymentExtended> [-Path <string>] [-Force]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has the following aliases,
  Save-AzSubscriptionDeploymentTemplate

## DESCRIPTION

Exports the Azure Resource Manager template that a subscription-scoped deployment was created from and writes it to a file on disk. The operation is read-only: it never creates or modifies resources. Azure Resource Manager returns the template exactly as it was submitted, with parameters and variables left unresolved, so the saved file can be fed straight back into `New-AzSubDeployment -TemplateFile`.

The cmdlet emits an object carrying the full path of the file that was written. Exporting a deployment that does not exist fails with `DeploymentNotFound`. Identify the deployment by `-Name`, or by piping a deployment object from `Get-AzSubDeployment`; a piped deployment is read from the subscription in its `Id`. With `-Name`, the subscription defaults to the active profile's subscription unless `-SubscriptionId` is supplied.

`-Path` follows the same rules as the legacy cmdlet: when it names an existing directory the file is written there as `<deployment name>.json`; any other value is treated as the file itself and gains a `.json` extension when it lacks one. A relative path is resolved against the current PowerShell location, and any missing parent directories are created. When `-Path` is omitted the file is written to the current location as `<deployment name>.json`.

If the destination file already exists the cmdlet fails rather than overwriting it. Pass `-Force` to overwrite.

## EXAMPLES

### Save a deployment template to the current directory

Writes `sub-infra-2026-06-18.json` to the current location.

```powershell
Save-AzSubDeploymentTemplate -Name sub-infra-2026-06-18
```

### Save a deployment template to a specific directory

The directory already exists, so the file is written as `C:\templates\sub-infra-2026-06-18.json`.

```powershell
Save-AzSubDeploymentTemplate -Name sub-infra-2026-06-18 -Path C:\templates
```

### Overwrite an existing file

Without `-Force` a second run against the same destination fails instead of replacing the file.

```powershell
Save-AzSubDeploymentTemplate -Name sub-infra-2026-06-18 -Path .\sub-infra.json -Force
```

### Save the template of a piped deployment

The deployment's `Id` carries its subscription, so the template is read from that subscription even when it is not the active one.

```powershell
Get-AzSubDeployment -Name sub-infra-2026-06-18 -SubscriptionId 00000000-0000-0000-0000-000000000000 | Save-AzSubDeploymentTemplate -Path C:\templates
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

### -Force

Overwrite the destination file when it already exists. Without this switch an existing file causes a terminating error and the file is left untouched.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
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

### -InputObject

A deployment object returned by `Get-AzSubDeployment`.
Its `Id` identifies the subscription and deployment whose template to save. Accepts pipeline input.

```yaml
Type: Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: SaveByInputObject
  Position: Named
  IsRequired: true
  ValueFromPipeline: true
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

The name of the deployment whose template to save.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: SaveByDeploymentName
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Path

The output path of the template file. An existing directory receives `<deployment name>.json`; any other value is used as the file name and gains a `.json` extension when it lacks one. Relative paths are resolved against the current PowerShell location. Defaults to the current location.

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
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Use the named profile for this command, overriding the active profile.

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

Azure subscription id. Defaults to the active profile's subscription.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: SaveByDeploymentName
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

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended

Accepts a subscription deployment object from the pipeline, for example the output of `Get-AzSubDeployment`.

### System.String

You can pipe the **Path** value to this cmdlet by property name.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Processors.DeploymentTemplateSaveResult

An object with a single `Path` property carrying the full path of the template file that was written.

## NOTES

The exported template is the template as submitted, not the resolved deployment output: parameter references and variables are preserved rather than replaced with their runtime values. Use `Get-AzSubDeployment` to inspect the parameter values a deployment actually ran with.

## RELATED LINKS


- [Get-AzSubDeployment](./Get-AzSubDeployment.md)
- [New-AzSubDeployment](./New-AzSubDeployment.md)
- [Test-AzSubDeployment](./Test-AzSubDeployment.md)
