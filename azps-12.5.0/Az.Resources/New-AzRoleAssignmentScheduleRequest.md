---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://learn.microsoft.com/powershell/module/az.resources/new-azroleassignmentschedulerequest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzRoleAssignmentScheduleRequest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/New-AzRoleAssignmentScheduleRequest.md
---

# New-AzRoleAssignmentScheduleRequest

## SYNOPSIS
Creates a role assignment schedule request.

## SYNTAX

```
New-AzRoleAssignmentScheduleRequest -Name <String> -Scope <String> [-Condition <String>]
 [-ConditionVersion <String>] [-ExpirationDuration <String>] [-ExpirationEndDateTime <DateTime>]
 [-ExpirationType <Type>] [-Justification <String>] [-LinkedRoleEligibilityScheduleId <String>]
 [-PrincipalId <String>] [-RequestType <RequestType>] [-RoleDefinitionId <String>]
 [-ScheduleInfoStartDateTime <DateTime>] [-TargetRoleAssignmentScheduleId <String>]
 [-TargetRoleAssignmentScheduleInstanceId <String>] [-TicketNumber <String>] [-TicketSystem <String>]
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Creates a role assignment schedule request.

## EXAMPLES

### Example 1: Create a new role assignment schedule request as Admin
```powershell
$guid = "12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
$startTime = Get-Date -Format o 
$scope = "/subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/"
New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId aaaaaaaa-bbbb-cccc-1111-222222222222 -RequestType AdminAssign -RoleDefinitionId subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime
```

```output
Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222 /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authori…
```

Creates a request to provision an active assignment of `roleDefinition` on the `scope` for the specified `principal`

### Example 2: Remove a role assignment schedule request as Admin
```powershell
$guid = "13f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
$startTime = Get-Date -Format o 
$scope = "/subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/"
New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId aaaaaaaa-bbbb-cccc-1111-222222222222 -RequestType AdminRemove -RoleDefinitionId subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime
```

```output
Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
13f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222 /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authori…
```

Creates a request to remove an active assignment of `roleDefinition` on the `scope` for the specified `principal`

### Example 3: Activate a new role assignment schedule request as user
```powershell
$guid = "12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
$startTime = Get-Date -Format o 
$scope = "/subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/"
New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId aaaaaaaa-bbbb-cccc-1111-222222222222 -RequestType SelfActivate -RoleDefinitionId subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime
```

```output
Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222 /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authori…
```

Creates a request to activate an eligible assignment of `roleDefinition` on the `scope` for the specified `principal`

### Example 4: Deactivate a role assignment schedule request as user
```powershell
$guid = "12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca"
$startTime = Get-Date -Format o 
$scope = "/subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/"
New-AzRoleAssignmentScheduleRequest -Name $guid -Scope $scope -ExpirationDuration PT1H -ExpirationType AfterDuration -PrincipalId aaaaaaaa-bbbb-cccc-1111-222222222222 -RequestType SelfDeactivate -RoleDefinitionId subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authorization/roleDefinitions/acdd72a7-3385-48ef-bd42-f606fba81ae7 -ScheduleInfoStartDateTime $startTime
```

```output
Name                                 Type                                                    Scope                                               RoleDefinitionId
----                                 ----                                                    -----                                               ----------------                                                                 
12f8978c-5d8d-4fbf-b4b6-2f43eeb43eca Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222 /subscriptions/aaaaaaaa-bbbb-cccc-1111-222222222222/providers/Microsoft.Authori…
```

Creates a request to deactivate an eligible assignment of `roleDefinition` on the `scope` for the specified `principal`

## PARAMETERS

### -Condition
The conditions on the role assignment.
This limits the resources it can be assigned to.
e.g.: @Resource[Microsoft.Storage/storageAccounts/blobServices/containers:ContainerName] StringEqualsIgnoreCase 'foo_storage_container'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConditionVersion
Version of the condition.
Currently accepted value is '2.0'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The DefaultProfile parameter is not functional.
Use the SubscriptionId parameter when available if executing the cmdlet against a different subscription.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirationDuration
Duration of the role assignment schedule in TimeSpan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirationEndDateTime
End DateTime of the role assignment schedule.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpirationType
Type of the role assignment schedule expiration

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Support.Type
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Justification
Justification for the role assignment

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinkedRoleEligibilityScheduleId
The linked role eligibility schedule id - to activate an eligibility.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the role assignment to create.
It can be any valid GUID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RoleAssignmentScheduleRequestName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrincipalId
The principal ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestType
The type of the role assignment schedule request.
Eg: SelfActivate, AdminAssign etc

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Support.RequestType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleDefinitionId
The role definition ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScheduleInfoStartDateTime
Start DateTime of the role assignment schedule.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope
The scope of the role assignment schedule request to create.
The scope can be any REST resource instance.
For example, use '/providers/Microsoft.Subscription/subscriptions/{subscription-id}/' for a subscription, '/providers/Microsoft.Subscription/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}' for a resource group, and '/providers/Microsoft.Subscription/subscriptions/{subscription-id}/resourceGroups/{resource-group-name}/providers/{resource-provider}/{resource-type}/{resource-name}' for a resource.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetRoleAssignmentScheduleId
The resultant role assignment schedule id or the role assignment schedule id being updated

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetRoleAssignmentScheduleInstanceId
The role assignment schedule instance id being updated

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TicketNumber
Ticket number for the role assignment

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TicketSystem
Ticket system name for the role assignment

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleAssignmentScheduleRequest

## NOTES

## RELATED LINKS
