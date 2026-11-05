---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Resources.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Resources
ms.date: 10-09-2026
PlatyPS schema version: 2024-05-01
title: New-AzRoleAssignment
---

# New-AzRoleAssignment

## SYNOPSIS

Create an Azure RBAC role assignment.

## SYNTAX

### SubscriptionScope (Default)

```
New-AzRoleAssignment -ObjectId <string> -RoleDefinitionId <string> [-SubscriptionId <string>]
 [-ObjectType <string>] [-Name <string>] [-Description <string>] [-Condition <string>]
 [-ConditionVersion <string>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceGroup

```
New-AzRoleAssignment -ResourceGroupName <string> -ObjectId <string> -RoleDefinitionId <string>
 [-SubscriptionId <string>] [-ObjectType <string>] [-Name <string>] [-Description <string>]
 [-Condition <string>] [-ConditionVersion <string>] [-Profile <string>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Scope

```
New-AzRoleAssignment -Scope <string> -ObjectId <string> -RoleDefinitionId <string>
 [-ObjectType <string>] [-Name <string>] [-Description <string>] [-Condition <string>]
 [-ConditionVersion <string>] [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Create an Azure role-based access control (RBAC) role assignment, granting the principal given by
`-ObjectId` the role given by `-RoleDefinitionId` at a scope. The scope defaults to the active
subscription and can be narrowed with `-ResourceGroupName` or overridden with `-Scope` (the two are
mutually exclusive). `-ObjectId` takes a GUID; `-RoleDefinitionId` takes a role definition GUID or a
fully-qualified role definition ID. Principal name/UPN/service-principal and role-name resolution are
not yet supported. The assignment name is generated when `-Name` is omitted. With a generated name,
re-running create for a principal, role, and scope that already has an assignment returns that existing
assignment instead of failing. Supplying an explicit `-Name` is stricter: the command then fails if a
differently-named assignment already grants that access.

## EXAMPLES

### Create a role assignment at a resource group scope

Grant the principal the given role over a resource group.

```powershell
New-AzRoleAssignment -ResourceGroupName my-rg -ObjectId 11111111-2222-3333-4444-555555555555 -RoleDefinitionId b24988ac-6180-42a0-ab88-20f7382dd24c
```

### Create a role assignment with a principal type and description

```powershell
New-AzRoleAssignment -Scope /subscriptions/00000000-0000-0000-0000-000000000000 -ObjectId 11111111-2222-3333-4444-555555555555 -RoleDefinitionId b24988ac-6180-42a0-ab88-20f7382dd24c -ObjectType ServicePrincipal -Description "grant CI access"
```

## PARAMETERS

### -Condition

Condition under which the principal is granted permission.

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

### -ConditionVersion

Version of the condition syntax (currently only '2.0').

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

### -Description

Description of the role assignment.

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

The role assignment name (a GUID). Generated when omitted.

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

### -ObjectId

The principal's object (principal) ID (GUID) to assign the role to.

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

### -ObjectType

The principal type of the assigned principal (User, Group, ServicePrincipal, or ForeignGroup).

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
- User
- Group
- ServicePrincipal
- ForeignGroup
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

Create the role assignment scoped to this resource group under the subscription. Mutually exclusive with -Scope.

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

The role definition ID (GUID) or a fully-qualified role definition ID to assign. Role name resolution is not yet supported.

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

### -Scope

Fully qualified scope to create the role assignment at (the grant target). Mutually exclusive with -ResourceGroupName. Defaults to the subscription scope.

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

The created `RoleAssignment`, including its id, name, and properties (role definition id, principal id and type, and scope).

## NOTES

Generated help for resources.

## RELATED LINKS


- [Online Version]()
