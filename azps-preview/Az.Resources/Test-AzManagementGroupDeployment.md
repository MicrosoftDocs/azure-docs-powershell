---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/19/2026
PlatyPS schema version: 2024-05-01
title: Test-AzManagementGroupDeployment
---

# Test-AzManagementGroupDeployment

## SYNOPSIS

Validate whether an ARM or Bicep template would be accepted for a management group deployment, without deploying it.

## SYNTAX

### __AllParameterSets

```
Test-AzManagementGroupDeployment -ManagementGroupId <string> -Location <string> [-Name <string>]
 [-TemplateObject <hashtable>] [-ParametersUri <string>] [-ParametersFile <string>]
 [-TemplateUri <string>] [-TemplateFile <string>] [-TemplateSpecId <string>] [-QueryString <string>]
 [-Mode <string>] [-Parameter <string[]>] [-ValidationLevel <string>] [-Profile <string>]
 [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

Asks Azure Resource Manager to validate a management-group deployment without creating or
modifying resources. Supply one template source: a local ARM JSON or Bicep file (`-TemplateFile`),
a nonempty template hash table (`-TemplateObject`), a remote ARM template (`-TemplateUri`),
or a template spec version (`-TemplateSpecId`). A `.bicepparam` file supplied with `-ParametersFile`
can provide its own template reference.

Supply template parameters with `-ParametersFile`, `-ParametersUri`, or a string array through
`-Parameter`. Inline values override matching values from a local parameters file.
`-ParametersUri` cannot be combined with `-ParametersFile` or `-Parameter`.
`-QueryString` supplies a query string for the template URI, not template parameter values.

Validation always uses `Incremental` mode, even when `-Mode Complete` is supplied.
On success, the cmdlet returns a `DeploymentValidateResult`. Validation failures are reported
on the error stream, not returned as validation-error objects in normal output.

## EXAMPLES

### Validate a Bicep template before deploying it

```powershell
Test-AzManagementGroupDeployment -ManagementGroupId myMG -Location eastus -TemplateFile .\main.bicep -ParametersFile .\main.parameters.json
```

### Validate a remote template with inline parameters

```powershell
Test-AzManagementGroupDeployment -ManagementGroupId myMG -Location eastus -Name mg-test -TemplateUri https://example.com/azuredeploy.json -Parameter policyName=audit-tags
```

### Validate a template hash table

```powershell
$template = @{
    '$schema' = 'https://schema.management.azure.com/schemas/2019-08-01/managementGroupDeploymentTemplate.json#'
    contentVersion = '1.0.0.0'
    resources = @()
}
Test-AzManagementGroupDeployment -ManagementGroupId myMG -Location eastus -TemplateObject $template
```

## PARAMETERS

### -Location

The Azure location where the deployment metadata is stored.

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

### -ManagementGroupId

The ID of the management group where the proposed deployment is validated.

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

### -Mode

Accepts `Incremental` (default) or `Complete` for compatibility with the create command.
Validation always uses `Incremental`, even when `Complete` is supplied.

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

### -Name

The name used for validation. Defaults to a new GUID when omitted.
Use 1-64 characters: letters, numbers, underscores, hyphens, periods, or parentheses.

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

### -Parameter

Template parameters supplied as a string array, for example
`-Parameter 'policyName=audit-tags','count=3'`. Each item can be a `Name=Value` pair,
a JSON parameters object, or a JSON parameters file path (optionally prefixed with `@`).
Values are parsed as JSON when possible; otherwise they are strings.
Later values override earlier values and matching keys in `-ParametersFile`.
Cannot be combined with `-ParametersUri`. Specify `-Parameter` once with all values.

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

### -ParametersFile

Path to a local ARM JSON parameters file or `.bicepparam` file. Inline `-Parameter` values
can override values from this file. A `.bicepparam` file can supply its own template reference.
Cannot be combined with `-ParametersUri`. Also accepts the alias `-TemplateParameterFile`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- TemplateParameterFile
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

### -ParametersUri

URI of a remote ARM JSON parameters file (for example, a blob URL).
Cannot be combined with `-ParametersFile` or `-Parameter`.
Include any required SAS token in this URI; `-QueryString` does not modify it.
Also accepts the alias `-TemplateParameterUri`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- TemplateParameterUri
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

### -QueryString

Optional SAS token or query string sent on the template link. Requires `-TemplateUri`.
A leading `?` or `&` is removed. This value is not added to `-ParametersUri`.

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

### -TemplateFile

Path to a local ARM JSON or Bicep template file.

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

### -TemplateObject

A nonempty hash table containing the ARM template.
Use this instead of `-TemplateFile`, `-TemplateUri`, or `-TemplateSpecId`.

```yaml
Type: System.Collections.Hashtable
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

### -TemplateSpecId

Resource ID of an existing template spec version to validate (for example, `/subscriptions/.../providers/Microsoft.Resources/templateSpecs/<spec>/versions/<version>`).

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

### -TemplateUri

URI of a remote ARM JSON template (for example, a blob URL).
Bicep source must be supplied locally with `-TemplateFile`, where it is compiled before submission.

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

### -ValidationLevel

Validation level sent to Azure Resource Manager. Standard values are `Template`, `Provider`,
and `ProviderNoRbac`. `ProviderNoRbac` uses read-permission checks instead of full deployment
permission checks; it does not skip all RBAC checks. When omitted, no level is sent and
Azure Resource Manager applies its default.

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

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentValidateResult

A `DeploymentValidateResult` describing the outcome of the validation, including the validated resources and the deployment properties Azure Resource Manager resolved. No resources are created or modified.

## NOTES

Validation is read-only: it never creates or modifies resources. Use `New-AzManagementGroupDeployment` to deploy once validation passes.

The CLI and PowerShell validation commands share the same result/error behavior, consistent
with the AzClips resource-group validation commands. Missing required parameters in a local
or inline template cause an error rather than an interactive prompt.
This cmdlet does not support `-WhatIf` or `-Confirm`.
Bicep templates and `.bicepparam` files require the Bicep CLI for local compilation.

Differences from Az.Resources: on success this cmdlet returns the `DeploymentValidateResult` instead of no output, and validation failures are written to the error stream instead of to the output stream as a list of `PSResourceManagerError` objects. The legacy parameter names `-TemplateParameterFile` and `-TemplateParameterUri` are accepted as aliases. `-TemplateParameterObject`, dynamic template parameters, `-SkipTemplateParameterPrompt`, `-SuppressDiagnostics`, and `-Pre` are not supported.

## RELATED LINKS

- [New-AzManagementGroupDeployment]()
- [Get-AzManagementGroupDeployment]()
