---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Resources
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: New-AzResourceGroupDeploymentWhatIf
---

# New-AzResourceGroupDeploymentWhatIf

## SYNOPSIS

Preview the changes an ARM or Bicep deployment would make to a resource group without applying them.

## SYNTAX

### \_\_AllParameterSets

```
New-AzResourceGroupDeploymentWhatIf -ResourceGroupName <string> -Name <string>
 [-TemplateUri <string>] [-TemplateFile <string>] [-TemplateSpecId <string>] [-QueryString <string>]
 [-ParametersUri <string>] [-ParametersFile <string>] [-Mode <string>] [-Parameter <string[]>]
 [-ValidationLevel <string>] [-ResultFormat <string>] [-SubscriptionId <string>]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Runs an ARM/Bicep what-if operation against an existing resource group and returns the set of resource changes the deployment would produce — additions, modifications, deletions, and no-ops — without creating or modifying any resources. The template is supplied either inline (`-TemplateFile`), via URL (`-TemplateUri`), or by referencing a template spec (`-TemplateSpecId`). Template parameters can be supplied via file, URI, query string, or as `Name=Value` pairs through `-Parameter`.
Use `-ResultFormat ResourceIdOnly` for a compact summary, or `-ResultFormat FullResourcePayloads` (default) to include the full predicted resource bodies.

## EXAMPLES

### Preview a Bicep deployment before applying it

Run a what-if for `main.bicep` with parameter file `main.parameters.json` as deployment `infra-prod-2026-06-18` against resource group `myrg`.

```powershell
New-AzResourceGroupDeploymentWhatIf -ResourceGroupName myrg -Name infra-prod-2026-06-18 -TemplateFile ./main.bicep -ParametersFile ./main.parameters.json -Mode Incremental
```

## PARAMETERS

### -Mode

Deployment mode used to evaluate the change set. Use `Incremental` (default) to add and update resources, or `Complete` to also report resources in the resource group that aren't declared in the template.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -Name

The name of the deployment. Used to track and reference the what-if operation in deployment history.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -Parameter

Template parameters supplied as inline `Name=Value` pairs. Use this when you don't have a parameters file. Repeat the flag or pass an array for multiple values.

```yaml
Type: System.String[]
DefaultValue: ""
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
HelpMessage: ""
```

### -ParametersFile

Path to a local ARM/Bicep parameters file (`*.parameters.json`).

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -ParametersUri

URI of a remote ARM/Bicep parameters file (for example, a blob URL).

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -QueryString

Optional SAS or query string appended to `-TemplateUri` / `-ParametersUri` when those URIs require authentication.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -ResourceGroupName

The name of the resource group to run the what-if against. The resource group must already exist.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -ResultFormat

The format of the what-if results. Use `FullResourcePayloads` (default) to include the full predicted resource bodies, or `ResourceIdOnly` for a compact list of affected resource IDs.

```yaml
Type: System.String
DefaultValue: ""
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
AcceptedValues:
    - FullResourcePayloads
    - ResourceIdOnly
HelpMessage: ""
```

### -SubscriptionId

The Azure subscription ID that owns the target resource group. Defaults to the current account context when omitted.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -TemplateFile

Path to a local ARM JSON or Bicep template file.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -TemplateSpecId

Resource ID of an existing template spec to evaluate (for example, `/subscriptions/.../providers/Microsoft.Resources/templateSpecs/<spec>/versions/<version>`).

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -TemplateUri

URI of a remote ARM/Bicep template (for example, a blob URL).

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### -ValidationLevel

What-if validation strictness. Common values are `Provider` (default) and `Template`. Use a stricter level to catch schema or parameter issues earlier.

```yaml
Type: System.String
DefaultValue: ""
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
HelpMessage: ""
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.WhatIfOperationResult

A `WhatIfOperationResult` describing the changes the deployment would apply if executed. No resources are created or modified; the caller can inspect the change list before running the real deployment.

## NOTES

What-if is a read-only preview: it never creates or modifies resources. Use `New-AzResourceGroupDeployment` to apply the changes once the preview looks correct.

## RELATED LINKS

- [New-AzResourceGroupDeployment]()
- [New-AzResourceGroup]()
- [Get-AzResourceGroup]()
