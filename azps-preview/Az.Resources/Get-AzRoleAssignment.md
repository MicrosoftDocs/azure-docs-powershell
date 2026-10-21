---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10-09-2026
PlatyPS schema version: 2024-05-01
title: Get-AzRoleAssignment
---

# Get-AzRoleAssignment

## SYNOPSIS

List Azure RBAC role assignments.

## SYNTAX

### SubscriptionScope (Default)

```
Get-AzRoleAssignment [-SubscriptionId <string>] [-ObjectId <string>] [-RoleDefinitionId <string>]
 [-IncludeInherited] [-ExpandPrincipalGroups] [-IncludeNestedScopes] [-Profile <string>]
 [<CommonParameters>]
```

### ResourceGroup

```
Get-AzRoleAssignment -ResourceGroupName <string> [-SubscriptionId <string>] [-ObjectId <string>]
 [-RoleDefinitionId <string>] [-IncludeInherited] [-ExpandPrincipalGroups] [-Profile <string>]
 [<CommonParameters>]
```

### Scope

```
Get-AzRoleAssignment -Scope <string> [-ObjectId <string>] [-RoleDefinitionId <string>]
 [-IncludeInherited] [-ExpandPrincipalGroups] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

List Azure role-based access control (RBAC) role assignments at a subscription, resource group, or scope.
The scope defaults to the active subscription and can be narrowed with `-ResourceGroupName` or overridden
with `-Scope` (the two are mutually exclusive). Use `-ObjectId` to filter to a single principal by its
object (principal) ID. Filtering by sign-in name, service-principal name, or role name is not yet supported.

By default only assignments made at the exact scope are listed. Use `-IncludeInherited` to also include
assignments inherited from ancestor scopes. (This widening switch is deliberately named `-IncludeInherited`
rather than classic's `-AtScope`, whose name signals the opposite — restricting to a scope — to avoid
surprising scripts migrated from classic.) Use `-ExpandPrincipalGroups` together with `-ObjectId` to also
include assignments the principal receives transitively through the groups it belongs to (it requires
an assignee). Use `-IncludeNestedScopes` to list assignments across the whole subscription including
every nested scope (resource groups and resources); it cannot be combined with `-Scope`,
`-ResourceGroupName`, or `-IncludeInherited`.

## EXAMPLES

### List role assignments in the subscription

List every role assignment in the active (or specified) subscription.

```powershell
Get-AzRoleAssignment -SubscriptionId 00000000-0000-0000-0000-000000000000
```

### List role assignments scoped to a resource group

List role assignments effective at the given resource group.

```powershell
Get-AzRoleAssignment -ResourceGroupName myrg
```

### List role assignments at an explicit scope

List role assignments at a fully qualified scope, such as a management group or a single resource.

```powershell
Get-AzRoleAssignment -Scope /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg
```

### List role assignments for a specific principal

Filter role assignments to the principal with the given object ID.

```powershell
Get-AzRoleAssignment -ObjectId 11111111-2222-3333-4444-555555555555
```

### List role assignments for a specific role

Filter role assignments to the given role definition ID. Role name resolution is not yet supported.

```powershell
Get-AzRoleAssignment -RoleDefinitionId b24988ac-6180-42a0-ab88-20f7382dd24c
```

### Include assignments inherited from ancestor scopes

By default only assignments made at the exact scope are listed. `-IncludeInherited` also includes assignments inherited from parent scopes.

```powershell
Get-AzRoleAssignment -Scope /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg -IncludeInherited
```

### Include assignments granted through group membership

`-ExpandPrincipalGroups` returns assignments the principal receives transitively through the groups it belongs to.

```powershell
Get-AzRoleAssignment -ObjectId 11111111-2222-3333-4444-555555555555 -ExpandPrincipalGroups
```

### List across the whole subscription including nested scopes

`-IncludeNestedScopes` lists assignments on the subscription and every resource group and resource beneath it. It cannot be combined with `-Scope` or `-ResourceGroupName`.

```powershell
Get-AzRoleAssignment -IncludeNestedScopes
```

## PARAMETERS

### -ExpandPrincipalGroups

When filtering by -ObjectId, also include assignments granted through groups the principal belongs to (transitive).

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
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

### -IncludeInherited

Include role assignments inherited from ancestor scopes. By default only assignments at the exact scope are listed.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
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

### -IncludeNestedScopes

List role assignments across the whole subscription, including every nested scope. Cannot be combined with -Scope or -ResourceGroupName.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: SubscriptionScope
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ObjectId

Filter to role assignments for this principal's object (principal) ID (GUID).

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
- Name: Scope
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

### -ResourceGroupName

List role assignments scoped to this resource group under the subscription. Mutually exclusive with -Scope.

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

### -RoleDefinitionId

Filter to role assignments for this role definition ID (GUID). Role name resolution is not yet supported.

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
- Name: Scope
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Scope

Fully qualified scope to list role assignments at. Mutually exclusive with -ResourceGroupName. Defaults to the subscription scope.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Resources.Models.RoleAssignment

One `RoleAssignment` object per matching assignment, including its id, name, and properties (role definition id, principal id and type, and scope).

## NOTES

Generated help for resources.

## RELATED LINKS


- [Online Version]()
