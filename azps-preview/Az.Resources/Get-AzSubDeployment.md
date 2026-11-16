---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/09/2026
PlatyPS schema version: 2024-05-01
title: Get-AzSubDeployment
---

# Get-AzSubDeployment

## SYNOPSIS

Get a single subscription-scope deployment by name, or list all deployments in a subscription.

## SYNTAX

### List (Default)

```
Get-AzSubDeployment [[-Name] <string>] [-SubscriptionId <string>] [-Profile <string>]
 [<CommonParameters>]
```

### Get

```
Get-AzSubDeployment [-Name] <string> [-SubscriptionId <string>] [-Profile <string>]
 [<CommonParameters>]
```

### GetByInputObject

```
Get-AzSubDeployment -InputObject <DeploymentExtended> [-Profile <string>] [<CommonParameters>]
```

## ALIASES

This cmdlet has the following aliases,
  Get-AzSubscriptionDeployment

## DESCRIPTION

Retrieves Azure Resource Manager deployments scoped to a subscription. Supply `-Name` to get a single deployment; omit it to list every subscription-scope deployment. Pipe a deployment object to read it again from the subscription in its `Id`, for example to refresh its provisioning state. Resource group deployments are not included; use `Get-AzResourceGroupDeployment` for those. With `-Name` or no name, the subscription defaults to the active profile's subscription unless `-SubscriptionId` is supplied.

## EXAMPLES

### Get a single deployment

Retrieve the subscription-scope deployment named `sub-infra-2026-06-18`.

```powershell
Get-AzSubDeployment -Name sub-infra-2026-06-18
```

### List every deployment in a subscription

Omit `-Name` to enumerate all subscription-scope deployments.

```powershell
Get-AzSubDeployment -SubscriptionId 00000000-0000-0000-0000-000000000000
```

### Refresh a piped deployment

Read each listed deployment again from the subscription in its `Id`.

```powershell
Get-AzSubDeployment -SubscriptionId 00000000-0000-0000-0000-000000000000 | Get-AzSubDeployment
```

## PARAMETERS

### -InputObject

A deployment object returned by `Get-AzSubDeployment`.
Its `Id` identifies the subscription and deployment to retrieve. Accepts pipeline input.

```yaml
Type: Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: GetByInputObject
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

The name of the deployment to retrieve. When supplied the cmdlet gets that single deployment; when omitted it lists every subscription-scope deployment.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: Get
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: List
  Position: 0
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

### -SubscriptionId

The Azure subscription that owns the deployment. Defaults to the active profile's subscription when omitted.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: List
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

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended

A `DeploymentExtended` for each matching deployment. The `Get` and `GetByInputObject` parameter sets emit exactly one object per deployment; the `List` parameter set emits one object per deployment, following paged results automatically.

## NOTES

This is a read-only operation. The legacy Az.Resources name `Get-AzSubscriptionDeployment` is accepted as an alias.

## RELATED LINKS

- [New-AzSubDeployment](./New-AzSubDeployment.md)
- [Get-AzSubDeploymentWhatIfResult](./Get-AzSubDeploymentWhatIfResult.md)
- [Stop-AzSubDeployment](./Stop-AzSubDeployment.md)
- [Remove-AzSubDeployment](./Remove-AzSubDeployment.md)
