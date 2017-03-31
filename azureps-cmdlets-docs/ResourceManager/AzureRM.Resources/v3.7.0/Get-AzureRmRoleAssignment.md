---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 488229AF-FD6D-4E1B-B3DA-E57CA781D91E
online version: 
schema: 2.0.0
---

# Get-AzureRmRoleAssignment

## SYNOPSIS
Lists Azure RBAC role assignments at the specified scope.
By default it lists all role assignments in the selected Azure subscription.
Use respective parameters to list assignments to a specific user, or to list assignments on a specific resource group or resource.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-AzureRmRoleAssignment [-RoleDefinitionName <String>] [-IncludeClassicAdministrators]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceWithObjectIdParameterSet
```
Get-AzureRmRoleAssignment -ObjectId <Guid> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] [-RoleDefinitionName <String>]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### RoleIdWithScopeAndObjectIdParameterSet
```
Get-AzureRmRoleAssignment [-ObjectId <Guid>] -RoleDefinitionId <Guid> [-Scope <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ObjectIdParameterSet
```
Get-AzureRmRoleAssignment -ObjectId <Guid> [-RoleDefinitionName <String>] [-ExpandPrincipalGroups]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceGroupWithObjectIdParameterSet
```
Get-AzureRmRoleAssignment -ObjectId <Guid> -ResourceGroupName <String> [-RoleDefinitionName <String>]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ScopeWithObjectIdParameterSet
```
Get-AzureRmRoleAssignment -ObjectId <Guid> [-RoleDefinitionName <String>] -Scope <String>
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceGroupWithSignInNameParameterSet
```
Get-AzureRmRoleAssignment -SignInName <String> -ResourceGroupName <String> [-RoleDefinitionName <String>]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceWithSignInNameParameterSet
```
Get-AzureRmRoleAssignment -SignInName <String> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] [-RoleDefinitionName <String>]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ScopeWithSignInNameParameterSet
```
Get-AzureRmRoleAssignment -SignInName <String> [-RoleDefinitionName <String>] -Scope <String>
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### SignInNameParameterSet
```
Get-AzureRmRoleAssignment -SignInName <String> [-RoleDefinitionName <String>] [-ExpandPrincipalGroups]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceGroupWithSPNParameterSet
```
Get-AzureRmRoleAssignment -ServicePrincipalName <String> -ResourceGroupName <String>
 [-RoleDefinitionName <String>] [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### ScopeWithSPNParameterSet
```
Get-AzureRmRoleAssignment -ServicePrincipalName <String> [-RoleDefinitionName <String>] -Scope <String>
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceWithSPNParameterSet
```
Get-AzureRmRoleAssignment -ServicePrincipalName <String> -ResourceGroupName <String> -ResourceName <String>
 -ResourceType <String> [-ParentResource <String>] [-RoleDefinitionName <String>]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### SPNParameterSet
```
Get-AzureRmRoleAssignment -ServicePrincipalName <String> [-RoleDefinitionName <String>]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceParameterSet
```
Get-AzureRmRoleAssignment -ResourceGroupName <String> -ResourceName <String> -ResourceType <String>
 [-ParentResource <String>] [-RoleDefinitionName <String>] [-IncludeClassicAdministrators]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ResourceGroupParameterSet
```
Get-AzureRmRoleAssignment -ResourceGroupName <String> [-RoleDefinitionName <String>]
 [-IncludeClassicAdministrators] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ScopeParameterSet
```
Get-AzureRmRoleAssignment [-RoleDefinitionName <String>] -Scope <String> [-IncludeClassicAdministrators]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The **Get-AzureRMRoleAssignment** cmdlet lists all role assignments that are effective on a scope.

Without any parameters, this command returns all the role assignments made under the subscription.
This list can  be filtered using filtering parameters for principal, role and scope.

The subject of the assignment must be specified.
To specify a user, use the *SignInName* or Azure AD *ObjectId* parameters.
To specify a security group, use the Azure AD *ObjectId* parameter.
And to specify an Azure AD application, use the *ServicePrincipalName* or *ObjectId* parameters.

The role that is being assigned must be specified using the *RoleDefinitionName* parameter.

The scope at which access is being granted may be specified.
It defaults to the selected subscription. 
The scope of the assignment can be specified using one of the following parameter combinations
        a.
Scope - This is the fully qualified scope starting with /subscriptions/\<subscriptionId\>.
This will filter assignments that are effective at that particular scope i.e.
all assignments at that scope and above.
        b.
ResourceGroupName - Name of any resource group under the subscription.
This will filter assignments effective at the specified resource group
        c.
ResourceName, ResourceType, ResourceGroupName and (optionally) ParentResource - Identifies a particular resource under the subscription and will filter assignments effective at that resource scope.

To determine what access a particular user has in the subscription, use the *ExpandPrincipalGroups* parameter.
This will list all roles assigned to the user, and to the groups that the user is member of.

Use the *IncludeClassicAdministrators* parameter to also display the subscription admins and co-admins.

## EXAMPLES

### Example 1: Get all role assignments in the subscription


```
PS C:\> Get-AzureRmRoleAssignment
```

This command gets all role assignments in the subscription.

### Example 2: Get all role assignments for a specified user


```
PS C:\> Get-AzureRmRoleAssignment -ResourceGroupName "TestRG" -SignInName "patty.fuller@contoso.com" -ExpandPrincipalGroups
```

This command gets all role assignments made to the user named patty.fuller@contoso.com, and the groups of which she is a member, at the TestRG scope or above.

### Example 3: Get all role assignments for the specified service principal


```
PS C:\> Get-AzureRmRoleAssignment -ServicePrincipalName "http://testapp1.com"
```

This command gets all role assignments of the specified service principal.

### Example 4: Get all role assignments for the specified scope


```
PS C:\> Get-AzureRmRoleAssignment -Scope "/subscriptions/96231a05-34ce-4eb4-aa6a-70759cbb5e83/resourcegroups/rg1/providers/Microsoft.Web/sites/site1"
```

This command gets role assignments at the site1 website scope.

## PARAMETERS

### -RoleDefinitionName
Specifies a role that is assigned to the service principal.
Reader, Contributor, Virtual Network Administrator, etc.

```yaml
Type: String
Parameter Sets: EmptyParameterSet, ResourceWithObjectIdParameterSet, ObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ScopeWithObjectIdParameterSet, ResourceGroupWithSignInNameParameterSet, ResourceWithSignInNameParameterSet, ScopeWithSignInNameParameterSet, SignInNameParameterSet, ResourceGroupWithSPNParameterSet, ScopeWithSPNParameterSet, ResourceWithSPNParameterSet, SPNParameterSet, ResourceParameterSet, ResourceGroupParameterSet, ScopeParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeClassicAdministrators
Indicates that the cmdlet also lists subscription classic administrators (co-admins, service admins, etc.) role assignments.

```yaml
Type: SwitchParameter
Parameter Sets: EmptyParameterSet, ResourceWithObjectIdParameterSet, ObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ScopeWithObjectIdParameterSet, ResourceGroupWithSignInNameParameterSet, ResourceWithSignInNameParameterSet, ScopeWithSignInNameParameterSet, SignInNameParameterSet, ResourceGroupWithSPNParameterSet, ScopeWithSPNParameterSet, ResourceWithSPNParameterSet, SPNParameterSet, ResourceParameterSet, ResourceGroupParameterSet, ScopeParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Specifies The Azure Active Directory ObjectId of the User, Group, or Service Principal.
Filters all assignments that are made to the specified principal.

```yaml
Type: Guid
Parameter Sets: ResourceWithObjectIdParameterSet, ObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ScopeWithObjectIdParameterSet
Aliases: Id, PrincipalId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: RoleIdWithScopeAndObjectIdParameterSet
Aliases: Id, PrincipalId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExpandPrincipalGroups
Indicaates that this cmdlet returns roles directly assigned to the user and to the groups of which the user is a member (transitively).
Supported only for a user principal.

```yaml
Type: SwitchParameter
Parameter Sets: ObjectIdParameterSet, SignInNameParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group.
Lists role assignments that are effective at the specified resource group.
When used in conjunction with the *ResourceName*, *ResourceType*, and *ParentResource* parameters, the command lists assignments effective at resources within the resource group.

```yaml
Type: String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceGroupWithObjectIdParameterSet, ResourceGroupWithSignInNameParameterSet, ResourceWithSignInNameParameterSet, ResourceGroupWithSPNParameterSet, ResourceWithSPNParameterSet, ResourceParameterSet, ResourceGroupParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceName
Specifies the name of the resource that this cmdlet gets.
This parameter must be used in conjunction with the *ResourceGroupName*, *ResourceType*, and *ParentResource* parameters.

```yaml
Type: String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceType
Specifies the resource type.
This parameter must be used in conjunction with the *ResourceGroupName*, *ResourceType*, and *ParentResource* parameters.

```yaml
Type: String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ParentResource
Specifies the parent resource in the hierarchy of the resource specified using the *ResourceName* parameter.
This parameter must be used in conjunction with the *ResourceGroupName*, *ResourceType*, and *ResourceName* parameters.

```yaml
Type: String
Parameter Sets: ResourceWithObjectIdParameterSet, ResourceWithSignInNameParameterSet, ResourceWithSPNParameterSet, ResourceParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope
Specifies the Scope of the role assignment.
In the format of the relative URI.
For instance, /subscriptions/9004a9fd-d58e-48dc-aeb2-4a4aec58606f/resourceGroups/TestRG.
It must start with "/subscriptions/{id}".
The command filters all assignments that are effective at that scope.

```yaml
Type: String
Parameter Sets: RoleIdWithScopeAndObjectIdParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ScopeWithObjectIdParameterSet, ScopeWithSignInNameParameterSet, ScopeWithSPNParameterSet, ScopeParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleDefinitionId
Specifeis the ID of the Role that is assigned to the principal.

```yaml
Type: Guid
Parameter Sets: RoleIdWithScopeAndObjectIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SignInName
Specifies the email address or the user principal name of the user.
Filters all assignments that are made to the specified user.

```yaml
Type: String
Parameter Sets: ResourceGroupWithSignInNameParameterSet, ResourceWithSignInNameParameterSet, ScopeWithSignInNameParameterSet, SignInNameParameterSet
Aliases: Email, UserPrincipalName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePrincipalName
Specifies the Service Principal Name of the service principal.
Filters all assignments that are made to the specified Azure AD application.

```yaml
Type: String
Parameter Sets: ResourceGroupWithSPNParameterSet, ScopeWithSPNParameterSet, ResourceWithSPNParameterSet, SPNParameterSet
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[New-AzureRmRoleAssignment](./New-AzureRmRoleAssignment.md)

[Remove-AzureRmRoleAssignment](./Remove-AzureRmRoleAssignment.md)

[Get-AzureRmRoleDefinition](./Get-AzureRmRoleDefinition.md)
