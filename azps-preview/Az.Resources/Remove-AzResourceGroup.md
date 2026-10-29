---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10/27/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzResourceGroup
---

# Remove-AzResourceGroup

## SYNOPSIS

Deletes a resource group and all resources it contains.

## SYNTAX

### RemoveByResourceGroupName (Default)

```
Remove-AzResourceGroup [-Name] <string> [-ForceDeletionType <string>] [-Force]
 [-SubscriptionId <string>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByResourceGroupId

```
Remove-AzResourceGroup -Id <string> [-ForceDeletionType <string>] [-Force]
 [-SubscriptionId <string>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.


## DESCRIPTION

Deletes a resource group, including its resources, deployments, and stored deployment operations.
Specify the resource group by name or by resource ID.
The cmdlet waits for deletion to finish and returns `True` when the operation succeeds.

## EXAMPLES

### Example 1: Delete a resource group by name

Delete a resource group in the active subscription without a confirmation prompt.

```powershell
Remove-AzResourceGroup -Name myresourcegroup -Force
```

### Example 2: Delete a resource group by resource ID

Delete a resource group by using its full ARM resource ID.

```powershell
Remove-AzResourceGroup -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myresourcegroup -Force
```

### Example 3: Preview a resource group deletion

Show what the cmdlet would delete without sending the delete request.

```powershell
Remove-AzResourceGroup -Name myresourcegroup -WhatIf
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

### -Force

Deletes the resource group without prompting for confirmation.
This parameter does not override `-WhatIf`.

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

### -ForceDeletionType

Specifies resource types that Azure should force delete.
Supported values include `Microsoft.Compute/virtualMachines`, `Microsoft.Compute/virtualMachineScaleSets`, and `Microsoft.Databricks/workspaces`.

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

### -Id

Specifies the full ARM resource ID of the resource group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ResourceGroupId
- ResourceId
ParameterSets:
- Name: RemoveByResourceGroupId
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

Specifies the name of the resource group.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ResourceGroupName
ParameterSets:
- Name: RemoveByResourceGroupName
  Position: 0
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: true
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Specifies a saved profile to use instead of the active profile.

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

Specifies the Azure subscription ID.
When omitted, the cmdlet uses the active profile's subscription.

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

Runs the command in a mode that only reports what would happen without performing the actions.

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

### System.String

You can pipe a resource group name or resource group ID to this cmdlet by property name.

## OUTPUTS

### System.Boolean

Returns `True` after the resource group deletion completes successfully.

## NOTES

Deleting a resource group permanently deletes all resources contained in the group.

## RELATED LINKS
