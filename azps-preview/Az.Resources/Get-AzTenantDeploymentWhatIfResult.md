---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 11/04/2026
PlatyPS schema version: 2024-05-01
title: Get-AzTenantDeploymentWhatIfResult
---

# Get-AzTenantDeploymentWhatIfResult

## SYNOPSIS

Preview the changes a tenant-scope deployment would make.

## SYNTAX

### Default (Default)

```
Get-AzTenantDeploymentWhatIfResult -Location <string> [-ResultFormat <string>] [-Name <string>]
 [-TemplateUri <string>] [-TemplateFile <string>] [-TemplateSpecId <string>] [-QueryString <string>]
 [-ParametersUri <string>] [-ParametersFile <string>] [-Parameter <string[]>]
 [-ValidationLevel <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

Runs a tenant scoped what-if operation. What-if is read-only: it predicts the changes (Create,
Modify, Delete, Deploy, NoChange, Ignore) a template would make without creating or modifying
any resources. Supply one template
source: a local ARM JSON or Bicep file (`-TemplateFile`), a remote ARM template (`-TemplateUri`),
or a template spec version (`-TemplateSpecId`). A `.bicepparam` file supplied with `-ParametersFile`
can provide its own template reference, so a separate template source is not required in that case.

Supply template parameters with `-ParametersFile`, `-ParametersUri`, or a string array through
`-Parameter`. Inline values override matching values from a local parameters file.
`-ParametersUri` cannot be combined with `-ParametersFile` or `-Parameter`.
`-QueryString` supplies a query string for the template URI, not template parameter values.
`-Name` defaults to a generated GUID when omitted. Tenant deployments always use `Incremental` mode.

`-ResultFormat` selects how much detail the predicted changes carry, `FullResourcePayloads`
(default) or `ResourceIdOnly`. The cmdlet waits for the what-if operation to finish and returns
the what-if result; if the operation fails, it raises an error.

## EXAMPLES

### Preview a Bicep file at tenant scope

```powershell
Get-AzTenantDeploymentWhatIfResult -Location eastus -Name tenant-infra -TemplateFile .\main.bicep -Parameter environment=prod
```

### Preview resource IDs only

```powershell
Get-AzTenantDeploymentWhatIfResult -Location eastus -TemplateFile .\main.bicep -ResultFormat ResourceIdOnly
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

### -Name

The name of the deployment. Defaults to a generated GUID when omitted.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
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
Cannot be combined with `-ParametersUri`.

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

### -ParametersUri

URI of a remote ARM JSON parameters file (for example, a blob URL).
Cannot be combined with `-ParametersFile` or `-Parameter`.
Include any required SAS token in this URI; `-QueryString` does not modify it.

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

### -ResultFormat

The format of the what-if results. FullResourcePayloads (default) or ResourceIdOnly.

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

### -TemplateSpecId

Resource ID of an existing template spec version to deploy (for example, `/subscriptions/.../providers/Microsoft.Resources/templateSpecs/<spec>/versions/<version>`).

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

### Microsoft.Azure.Azclips.Extensions.Resources.Models.WhatIfOperationResult

The raw what-if result: the operation status and the predicted resource changes.

## NOTES

Missing required parameters in a local or inline template cause an error rather than an
interactive prompt. Bicep templates and `.bicepparam` files are compiled locally before submission.
The Bicep CLI must be installed to use these file types.

Differences from Az.Resources: the cmdlet returns the raw `WhatIfOperationResult` instead of `PSWhatIfOperationResult`, and does not print formatted what-if text. `-ExcludeChangeType`, `-SkipTemplateParameterPrompt`, `-TemplateObject`, `-TemplateParameterObject`, and `-Pre` are not supported.

## RELATED LINKS

- [New-AzTenantDeployment](New-AzTenantDeployment.md)
- [Test-AzTenantDeployment](Test-AzTenantDeployment.md)
