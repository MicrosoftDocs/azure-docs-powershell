---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/27/2026
PlatyPS schema version: 2024-05-01
title: Get-AzResourceGroupDeployment
---

# Get-AzResourceGroupDeployment

## SYNOPSIS

Get a single resource group deployment by name, or list all deployments in a resource group.

## SYNTAX

### List

```
Get-AzResourceGroupDeployment [-ResourceGroupName] <string> [-SubscriptionId <string>]
 [-Profile <string>] [<CommonParameters>]
```

### Get

```
Get-AzResourceGroupDeployment [-ResourceGroupName] <string> [-Name] <string>
 [-SubscriptionId <string>] [-Profile <string>] [<CommonParameters>]
```

### GetById

```
Get-AzResourceGroupDeployment -Id <string> [-Profile <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Retrieves Azure Resource Manager deployments scoped to a resource group. Supply `-Name` to get a single deployment, or `-Id` with the deployment's fully qualified resource id; omit both to list every deployment in the resource group. The returned `DeploymentExtended` objects carry the ARM shape (`Name`, `Properties.*`) plus top-level `DeploymentName`, `ResourceGroupName`, `ProvisioningState`, `Timestamp`, `Mode`, `CorrelationId`, `Parameters`, `Outputs`, `TemplateLink`, and `OnErrorDeployment` properties for compatibility with Az.Resources scripts. The subscription defaults to the active profile's subscription unless `-SubscriptionId` is supplied.

## EXAMPLES

### Get a single deployment

Retrieve the deployment named `infra-prod-2026-06-18` from resource group `myrg`.

```powershell
Get-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18
```

### List every deployment in a resource group

Omit `-Name` to enumerate all deployments in `myrg`.

```powershell
Get-AzResourceGroupDeployment -ResourceGroupName myrg
```

### Read the outputs of a deployment

Retrieve a deployment and inspect the values its template returned.

```powershell
$deployment = Get-AzResourceGroupDeployment -ResourceGroupName myrg -Name infra-prod-2026-06-18
$deployment.Outputs
```

### Get a deployment by resource id

```powershell
Get-AzResourceGroupDeployment -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Resources/deployments/infra-prod-2026-06-18
```

## PARAMETERS

### -Id

The fully qualified resource id of the deployment, in the form `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentId
- ResourceId
ParameterSets:
- Name: GetById
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

The name of the deployment to retrieve. When supplied the cmdlet gets that single deployment; when omitted it lists every deployment in the resource group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- DeploymentName
ParameterSets:
- Name: Get
  Position: 1
  IsRequired: true
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

### -ResourceGroupName

The name of the resource group that contains the deployments.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
- Name: List
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
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

### System.String

You can pipe the **ResourceGroupName** and **Name** values to this cmdlet by property name, for example the output of `Get-AzResourceGroupDeployment`.

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.DeploymentExtended

A `DeploymentExtended` for each matching deployment. The `Get` and `GetById` parameter sets emit exactly one object; the `List` parameter set emits one object per deployment in the resource group, following paged results automatically.

## NOTES

This is a read-only operation. Use `New-AzResourceGroupDeployment` to create a deployment and `New-AzResourceGroupDeploymentWhatIf` to preview one.

## RELATED LINKS


- [New-AzResourceGroupDeployment](New-AzResourceGroupDeployment.md)
- [New-AzResourceGroupDeploymentWhatIf](New-AzResourceGroupDeploymentWhatIf.md)
- [Get-AzResourceGroup](Get-AzResourceGroup.md)
