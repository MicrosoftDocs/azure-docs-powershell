---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/09/2026
PlatyPS schema version: 2024-05-01
title: Test-AzSubDeployment
---

# Test-AzSubDeployment

## SYNOPSIS

Validate whether an ARM or Bicep template would be accepted for a subscription-scope deployment, without deploying it.

## SYNTAX

### Default (Default)

```
Test-AzSubDeployment -Name <string> -Location <string> -Mode <string> [-TemplateUri <string>]
 [-TemplateFile <string>] [-TemplateSpecId <string>] [-TemplateObject <hashtable>]
 [-QueryString <string>] [-ParametersUri <string>] [-ParametersFile <string>]
 [-Parameter <string[]>] [-ValidationLevel <string>] [-SubscriptionId <string>] [-Profile <string>]
 [<CommonParameters>]
```

## ALIASES

This cmdlet has the following aliases,
  Test-AzSubscriptionDeployment

## DESCRIPTION

Asks Azure Resource Manager whether a template is syntactically correct and would be accepted for deployment at the subscription scope, without creating or modifying any resources. The template is supplied as a local ARM JSON or Bicep file (`-TemplateFile`), a URL (`-TemplateUri`), a template spec (`-TemplateSpecId`), or an inline hashtable (`-TemplateObject`). Bicep files are compiled with the Bicep CLI, which must be installed. Template parameters can be supplied via file (`-ParametersFile`), URI (`-ParametersUri`), or as `Name=Value` pairs through `-Parameter`. `-QueryString` supplies a query string for the template URI, not template parameter values.

When the template is valid the validation result is returned; when it is not, the cmdlet writes the validation errors and terminates with a non-zero exit code.

## EXAMPLES

### Validate a Bicep file with inline parameters

Validate `main.bicep` as deployment `sub-infra-2026-06-18`, and supply its parameters inline.

```powershell
Test-AzSubDeployment -Name sub-infra-2026-06-18 -Location eastus -Mode Incremental -TemplateFile ./main.bicep -Parameter rgName=demo-rg, rgLocation=eastus
```

### Validate a local template with a local parameters file

```powershell
Test-AzSubDeployment -Name create-rg -Location eastus -Mode Incremental -TemplateFile ./create-rg.json -ParametersFile ./create-rg.parameters.json
```

### Validate a remote template with a remote parameters file

Validate a template hosted at a URL as deployment `sub-infra-2026-06-18`.

```powershell
Test-AzSubDeployment -Name sub-infra-2026-06-18 -Location eastus -Mode Incremental -TemplateUri https://contoso.blob.core.windows.net/templates/create-rg.json -ParametersUri https://contoso.blob.core.windows.net/templates/create-rg.parameters.json
```

### Validate a template spec

```powershell
Test-AzSubDeployment -Name sub-infra-spec -Location westus2 -Mode Incremental -TemplateSpecId /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup/providers/Microsoft.Resources/templateSpecs/myTemplateSpec/versions/1.0
```

## PARAMETERS

### -Location

The Azure region that stores the deployment metadata, for example `eastus`. Subscription-scope deployments have no resource group to inherit a region from, so a location is required.

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

The deployment mode, `Incremental` or `Complete`.

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
AcceptedValues:
- Incremental
- Complete
HelpMessage: ''
```

### -Name

The deployment name to validate.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
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

Template parameters supplied as inline `Name=Value` pairs. Use this when you don't have a parameters file. Pass an array for multiple values. Values are parsed as JSON when possible, and otherwise treated as strings. Inline values overlay same-named keys from `-ParametersFile` and cannot be combined with `-ParametersUri`.

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

Path to a local ARM/Bicep parameters file (`*.parameters.json` or `*.bicepparam`). A `.bicepparam` file names its own template through its `using` declaration, so no template parameter is needed alongside it.

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

URI of a remote ARM parameters file (for example, a blob URL).
Include any required SAS token in this URI; `-QueryString` does not modify it.

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

### -SubscriptionId

The Azure subscription that owns the deployment. Defaults to the active profile's subscription when omitted.

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

An inline ARM template supplied as a hashtable, for example the result of `Get-Content ./azuredeploy.json -Raw | ConvertFrom-Json -AsHashtable`.

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

Resource ID of an existing template spec version to deploy (for example, `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Resources/templateSpecs/{name}/versions/{version}`).

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

Deployment validation strictness. One of `Template`, `Provider`, or `ProviderNoRbac`. Use a stricter level to catch schema or parameter issues earlier.

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

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentValidateResult

A `DeploymentValidateResult` describing the outcome of the validation, including the deployment properties Azure Resource Manager resolved. No resources are created or modified.

## NOTES

Validation is read-only: it never creates or modifies resources. A non-zero exit code means the template would be rejected. Use `New-AzSubDeployment` to deploy once validation passes.

Differences from Az.Resources: on success this cmdlet returns the `DeploymentValidateResult` instead of no output, and validation failures are written to the error stream instead of the output stream. The legacy name `Test-AzSubscriptionDeployment` and the parameter names `-DeploymentName`, `-TemplateParameterFile`, and `-TemplateParameterUri` are accepted as aliases.

## RELATED LINKS

- [New-AzSubDeployment](./New-AzSubDeployment.md)
- [Get-AzSubDeployment](./Get-AzSubDeployment.md)
- [Get-AzSubDeploymentWhatIfResult](./Get-AzSubDeploymentWhatIfResult.md)
- [Test-AzResourceGroupDeployment](./Test-AzResourceGroupDeployment.md)
