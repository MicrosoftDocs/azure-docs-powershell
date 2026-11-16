---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/09/2026
PlatyPS schema version: 2024-05-01
title: Get-AzSubDeploymentWhatIfResult
---

# Get-AzSubDeploymentWhatIfResult

## SYNOPSIS

Preview the changes an ARM or Bicep template would make at the subscription scope, without deploying it.

## SYNTAX

### Default (Default)

```
Get-AzSubDeploymentWhatIfResult -Location <string> [-Name <string>] [-TemplateUri <string>]
 [-TemplateFile <string>] [-TemplateSpecId <string>] [-TemplateObject <hashtable>]
 [-QueryString <string>] [-ParametersUri <string>] [-ParametersFile <string>]
 [-Parameter <string[]>] [-ValidationLevel <string>] [-ResultFormat <string>]
 [-SubscriptionId <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has the following aliases,
  Get-AzSubscriptionDeploymentWhatIfResult

## DESCRIPTION

Runs an ARM/Bicep what-if operation at the subscription scope and returns the set of resource changes the deployment would produce — additions, modifications, deletions, and no-ops — without creating or modifying any resources. The template is supplied as a local ARM JSON or Bicep file (`-TemplateFile`), a URL (`-TemplateUri`), a template spec (`-TemplateSpecId`), or an inline hashtable (`-TemplateObject`). Bicep files are compiled with the Bicep CLI, which must be installed. Template parameters can be supplied via file (`-ParametersFile`), URI (`-ParametersUri`), or as `Name=Value` pairs through `-Parameter`. `-QueryString` supplies a query string for the template URI, not template parameter values.

Use `-ResultFormat ResourceIdOnly` for a compact summary, or `-ResultFormat FullResourcePayloads` (default) to include the full predicted resource bodies.

## EXAMPLES

### Preview a Bicep file with inline parameters

Preview the changes `main.bicep` would make, and supply its parameters inline.

```powershell
Get-AzSubDeploymentWhatIfResult -Location eastus -TemplateFile ./main.bicep -Parameter rgName=demo-rg, rgLocation=eastus
```

### Preview a local template with a local parameters file

```powershell
Get-AzSubDeploymentWhatIfResult -Name create-rg -Location eastus -TemplateFile ./create-rg.json -ParametersFile ./create-rg.parameters.json
```

### Preview a remote template and return only resource IDs

```powershell
Get-AzSubDeploymentWhatIfResult -Name sub-infra-2026-06-18 -Location eastus -TemplateUri https://contoso.blob.core.windows.net/templates/create-rg.json -ParametersUri https://contoso.blob.core.windows.net/templates/create-rg.parameters.json -ResultFormat ResourceIdOnly
```

### Preview a template spec

```powershell
Get-AzSubDeploymentWhatIfResult -Name sub-infra-spec -Location westus2 -TemplateSpecId /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myResourceGroup/providers/Microsoft.Resources/templateSpecs/myTemplateSpec/versions/1.0
```

## PARAMETERS

### -Location

The Azure region that stores the what-if operation metadata, for example `eastus`. Subscription-scope deployments have no resource group to inherit a region from, so a location is required.

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

The deployment name to evaluate. When omitted, it defaults to the template file or URI name, or to a new GUID when that name is not a valid deployment name.

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

### -ResultFormat

The format of the what-if results. Use `FullResourcePayloads` (default) to include the full predicted resource bodies, or `ResourceIdOnly` for a compact list of affected resource IDs.

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
AcceptedValues:
- FullResourcePayloads
- ResourceIdOnly
HelpMessage: ''
```

### -SubscriptionId

The Azure subscription to evaluate the deployment against. Defaults to the active profile's subscription when omitted.

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

Resource ID of an existing template spec version to evaluate (for example, `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Resources/templateSpecs/{name}/versions/{version}`).

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

What-if validation strictness. One of `Template`, `Provider`, or `ProviderNoRbac`. Use a stricter level to catch schema or parameter issues earlier.

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

### Microsoft.Azure.Azclips.Extensions.Resources.Models.WhatIfOperationResult

A `WhatIfOperationResult` describing the changes the deployment would apply if executed. No resources are created or modified; the caller can inspect the change list before running the real deployment.

## NOTES

What-if is a read-only preview: it never creates or modifies resources. As in Az.Resources, the preview always uses `Incremental` mode, so there is no `-Mode` parameter. Use `New-AzSubDeployment` to apply the changes once the preview looks correct.

Differences from Az.Resources: the parameters `-ExcludeChangeType`, `-TemplateParameterObject`, `-Pre`, and `-SkipTemplateParameterPrompt` are not supported. The legacy name `Get-AzSubscriptionDeploymentWhatIfResult` and the parameter names `-DeploymentName`, `-TemplateParameterFile`, and `-TemplateParameterUri` are accepted as aliases.

## RELATED LINKS

- [New-AzSubDeployment](./New-AzSubDeployment.md)
- [Test-AzSubDeployment](./Test-AzSubDeployment.md)
- [New-AzResourceGroupDeploymentWhatIf](./New-AzResourceGroupDeploymentWhatIf.md)
