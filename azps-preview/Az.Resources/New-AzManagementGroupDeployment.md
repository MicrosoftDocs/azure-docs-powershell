---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/19/2026
PlatyPS schema version: 2024-05-01
title: New-AzManagementGroupDeployment
---

# New-AzManagementGroupDeployment

## SYNOPSIS

Deploy an ARM or Bicep template at management group scope.

## SYNTAX

### __AllParameterSets

```
New-AzManagementGroupDeployment -Name <string> -ManagementGroupId <string> -Location <string>
 [-ParametersUri <string>] [-ParametersFile <string>] [-TemplateUri <string>]
 [-TemplateFile <string>] [-TemplateSpecId <string>] [-QueryString <string>] [-Mode <string>]
 [-Parameter <string[]>] [-ValidationLevel <string>] [-Profile <string>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

Validates and then submits a deployment to the specified management group. Supply one template
source: a local ARM JSON or Bicep file (`-TemplateFile`), a remote ARM template (`-TemplateUri`),
or a template spec version (`-TemplateSpecId`). A `.bicepparam` file supplied with `-ParametersFile`
can provide its own template reference, so a separate template source is not required in that case.

Supply template parameters with `-ParametersFile`, `-ParametersUri`, or a string array through
`-Parameter`. Inline values override matching values from a local parameters file.
`-ParametersUri` cannot be combined with `-ParametersFile` or `-Parameter`.
`-QueryString` supplies a query string for the template URI, not template parameter values.

Validation always uses `Incremental` mode. If validation passes, the cmdlet deploys using the
selected `-Mode`, waits for completion, and returns the final deployment.

## EXAMPLES

### Deploy a Bicep file to a management group

Submit `main.bicep` with parameter file `main.parameters.json` as deployment `mg-infra` to management group `myMG`.

```powershell
New-AzManagementGroupDeployment -ManagementGroupId myMG -Location eastus -Name mg-infra -TemplateFile .\main.bicep -ParametersFile .\main.parameters.json
```

### Deploy a remote template with inline parameters

```powershell
New-AzManagementGroupDeployment -ManagementGroupId myMG -Location eastus -Name mg-infra -TemplateUri https://example.com/azuredeploy.json -Parameter policyName=audit-tags
```

### Deploy using a Bicep parameters file

The `.bicepparam` file supplies the template reference through its `using` declaration.

```powershell
New-AzManagementGroupDeployment -ManagementGroupId myMG -Location eastus -Name mg-infra -ParametersFile .\main.bicepparam
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

The ID of the management group that receives the deployment.

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

The mode sent to Azure Resource Manager for the actual deployment: `Incremental` (default)
or `Complete`. Azure Resource Manager determines whether the mode is supported at this scope.
Validation before deployment always uses `Incremental`; it does not validate `Complete` mode.

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

The required deployment name. Use 1-64 characters: letters, numbers, underscores, hyphens,
periods, or parentheses.

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

### -WhatIf

Shows PowerShell's create action message without validating or deploying the template.
This is not an ARM what-if preview: it does not return predicted resource changes.

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

### None

This cmdlet does not accept pipeline input.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended

The completed `DeploymentExtended` object containing the deployment name, provisioning state,
outputs declared by the template, and correlation ID. No output is returned when `-WhatIf`
or a declined confirmation skips the deployment.

## NOTES

The deployment is validated first using `Incremental` mode; a validation failure stops the cmdlet before anything is deployed. The actual deployment uses the selected `-Mode`.

Missing required parameters in a local or inline template cause an error rather than an
interactive prompt. Bicep templates and `.bicepparam` files are compiled locally before submission.
The Bicep CLI must be installed to use these file types.
The standard PowerShell `-WhatIf` switch only skips the action; it does not run ARM what-if.

Differences from Az.Resources: the cmdlet returns the `DeploymentExtended` model instead of `PSDeployment`. Template parameters are passed with `-Parameter`, `-ParametersFile`, or `-ParametersUri` instead of dynamic parameters, `-TemplateObject`, or `-TemplateParameterObject`. `-AsJob`, `-Tag`, `-DeploymentDebugLogLevel`, `-SkipTemplateParameterPrompt`, the what-if confirmation parameters, and `-Pre` are not supported.

## RELATED LINKS

- [Test-AzManagementGroupDeployment]()
- [Get-AzManagementGroupDeployment]()
- [Remove-AzManagementGroupDeployment]()
