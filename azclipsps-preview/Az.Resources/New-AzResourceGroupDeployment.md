---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ""
Locale: en-US
Module Name: Resources
ms.date: 08/06/2026
PlatyPS schema version: 2024-05-01
title: New-AzResourceGroupDeployment
---

# New-AzResourceGroupDeployment

## SYNOPSIS

Deploy an ARM or Bicep template into an existing resource group.

## SYNTAX

### \_\_AllParameterSets

```
New-AzResourceGroupDeployment -ResourceGroupName <string> -Name <string> [-TemplateUri <string>]
 [-TemplateFile <string>] [-TemplateSpecId <string>] [-QueryString <string>]
 [-ParametersUri <string>] [-ParametersFile <string>] [-Mode <string>] [-Parameter <string[]>]
 [-RollbackOnError] [-RollbackToDeploymentName <string>] [-ValidationLevel <string>]
 [-SubscriptionId <string>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Submits a deployment to the specified resource group using an ARM/Bicep template supplied either inline (`-TemplateFile`), via URL (`-TemplateUri`), or by referencing a template spec (`-TemplateSpecId`). Template parameters can be supplied via file, URI, query string, or as `Name=Value` pairs through `-Parameter`.
Use `-Mode Complete` for full reconciliation, or `-Mode Incremental` (default) to add and update without removing untracked resources.

## EXAMPLES

### Deploy a Bicep file into an existing resource group

Submit `main.bicep` along with parameter file `main.parameters.json` as deployment `infra-prod-2026-06-16` into resource group `myrg`.

```powershell
New-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-16 -TemplateFile ./main.bicep -ParametersFile ./main.parameters.json -Mode Incremental
```

## PARAMETERS

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
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
HelpMessage: ""
```

### -Mode

Deployment mode. Use `Incremental` (default) to add and update resources, or `Complete` to delete resources in the resource group that aren't declared in the template.

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

The name of the deployment. Used to track and reference the deployment in deployment history.

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

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

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

The name of the resource group that will receive the deployment. The resource group must already exist.

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

### -RollbackOnError

If the deployment fails, automatically roll back to the last successful deployment in this resource group.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### -RollbackToDeploymentName

Name of an explicit prior deployment to roll back to on failure. Implies the rollback behaviour of `-RollbackOnError`.

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

Resource ID of an existing template spec to deploy (for example, `/subscriptions/.../providers/Microsoft.Resources/templateSpecs/<spec>/versions/<version>`).

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

Deployment validation strictness. Common values are `Provider` (default) and `Template`. Use a stricter level to catch schema or parameter issues earlier.

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

### -WhatIf

Runs the command in a mode that only reports what would happen without performing the actions.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ""
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
HelpMessage: ""
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended

The completed `DeploymentExtended` object containing the deployment name, provisioning state, outputs declared by the template, and correlation ID.

## NOTES

The target resource group must already exist. Use `New-AzResourceGroup` to create it first when bootstrapping a new environment.

## RELATED LINKS

- [New-AzResourceGroup]()
- [Get-AzResourceGroup]()
