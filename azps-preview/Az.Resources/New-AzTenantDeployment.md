---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 11/04/2026
PlatyPS schema version: 2024-05-01
title: New-AzTenantDeployment
---

# New-AzTenantDeployment

## SYNOPSIS

Deploy an ARM or Bicep template at tenant scope.

## SYNTAX

### Default (Default)

```
New-AzTenantDeployment -Location <string> [-NoWait] [-Name <string>] [-TemplateUri <string>]
 [-TemplateFile <string>] [-TemplateSpecId <string>] [-QueryString <string>]
 [-ParametersUri <string>] [-ParametersFile <string>] [-Parameter <string[]>]
 [-ValidationLevel <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

Validates and then submits a deployment at tenant scope. Supply one template
source: a local ARM JSON or Bicep file (`-TemplateFile`), a remote ARM template (`-TemplateUri`),
or a template spec version (`-TemplateSpecId`). A `.bicepparam` file supplied with `-ParametersFile`
can provide its own template reference, so a separate template source is not required in that case.

Supply template parameters with `-ParametersFile`, `-ParametersUri`, or a string array through
`-Parameter`. Inline values override matching values from a local parameters file.
`-ParametersUri` cannot be combined with `-ParametersFile` or `-Parameter`.
`-QueryString` supplies a query string for the template URI, not template parameter values.
`-Name` defaults to a generated GUID when omitted. Tenant deployments always use `Incremental` mode.

If validation passes, the cmdlet deploys, waits for completion, and returns the final deployment.
With `-NoWait`, the cmdlet returns the deployment's initial state as soon as the deployment is
submitted instead of waiting for it to finish; validation still runs first.

## EXAMPLES

### Deploy a Bicep file at tenant scope

Submit `main.bicep` with parameter file `main.parameters.json` as deployment `tenant-infra`.

```powershell
New-AzTenantDeployment -Location eastus -Name tenant-infra -TemplateFile .\main.bicep -ParametersFile .\main.parameters.json
```

### Deploy a remote template with inline parameters

```powershell
New-AzTenantDeployment -Location eastus -Name tenant-infra -TemplateUri https://example.com/azuredeploy.json -Parameter policyName=audit-tags
```

### Submit a deployment without waiting for it to finish

Return the deployment as soon as it is submitted, then check on it later with `Get-AzTenantDeployment`.

```powershell
New-AzTenantDeployment -Location eastus -Name tenant-infra -TemplateFile .\main.bicep -NoWait
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

### -NoWait

Return once the deployment is submitted and output its initial state, instead of waiting for it to finish. Validation still runs first. Does not create a PowerShell job.

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
outputs declared by the template, and correlation ID. With `-NoWait`, the deployment as returned
when it was submitted, typically with provisioning state `Accepted` or `Running`.

## NOTES

The deployment is validated first using `Incremental` mode; a validation failure stops the cmdlet before anything is deployed.

Missing required parameters in a local or inline template cause an error rather than an
interactive prompt. Bicep templates and `.bicepparam` files are compiled locally before submission.
The Bicep CLI must be installed to use these file types.

Differences from Az.Resources: the cmdlet returns the `DeploymentExtended` model instead of `PSDeployment`. Template parameters are passed with `-Parameter`, `-ParametersFile`, or `-ParametersUri` instead of dynamic parameters, `-TemplateObject`, or `-TemplateParameterObject`. `-NoWait` returns the submitted deployment directly instead of creating a PowerShell job; `-AsJob` is not supported. `-Tag`, `-DeploymentDebugLogLevel`, `-SkipTemplateParameterPrompt`, the `-WhatIf`/`-Confirm` what-if confirmation, and `-Pre` are not supported.

## RELATED LINKS

- [Test-AzTenantDeployment](Test-AzTenantDeployment.md)
- [Get-AzTenantDeploymentWhatIfResult](Get-AzTenantDeploymentWhatIfResult.md)
- [Get-AzTenantDeployment](Get-AzTenantDeployment.md)
