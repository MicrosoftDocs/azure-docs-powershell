---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10-09-2026
PlatyPS schema version: 2024-05-01
title: Remove-AzRoleAssignment
---

# Remove-AzRoleAssignment

## SYNOPSIS

Delete an Azure RBAC role assignment.

## SYNTAX

### SubscriptionScope (Default)

```
Remove-AzRoleAssignment -Name <string> [-SubscriptionId <string>] [-Profile <string>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ResourceGroup

```
Remove-AzRoleAssignment -ResourceGroupName <string> -Name <string> [-SubscriptionId <string>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Scope

```
Remove-AzRoleAssignment -Scope <string> -Name <string> [-Profile <string>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Delete an Azure role-based access control (RBAC) role assignment by scope and name. The scope
defaults to the active subscription and can be narrowed with `-ResourceGroupName` or overridden with
`-Scope` (the two are mutually exclusive). `-Name` (the assignment's GUID) is required: this targets
exactly one already-known assignment. Deleting by principal/role filter, or deleting every assignment
at a scope, is not supported — use `Get-AzRoleAssignment` first to find the assignment's name.

## EXAMPLES

### Delete a role assignment by name at a resource group scope

```powershell
Remove-AzRoleAssignment -ResourceGroupName my-rg -Name aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee
```

### Delete a role assignment at an explicit scope

```powershell
Remove-AzRoleAssignment -Scope /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/my-rg -Name aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee
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

### -Name

The role assignment name (a GUID) to delete.

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

### -ResourceGroupName

Delete the role assignment scoped to this resource group under the subscription. Mutually exclusive with -Scope.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ResourceGroup
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Scope

Fully qualified scope to delete the role assignment from (the delete target). Mutually exclusive with -ResourceGroupName. Defaults to the subscription scope.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Scope
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubscriptionId

Azure Subscription Id. Defaults to the active profile's subscription.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: SubscriptionScope
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: ResourceGroup
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

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.RoleAssignment

The deleted `RoleAssignment`, including its id, name, and properties (role definition id, principal id and type, and scope). ARM returns no content when the assignment did not exist, so nothing is written to the pipeline in that case.

## NOTES

Generated help for resources.

## RELATED LINKS


- [Online Version]()
