---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 7740AC3B-F643-4F8D-8DC5-ACBF59323BD8
online version: 
schema: 2.0.0
---

# Get-AzureRmRoleDefinition

## SYNOPSIS
Lists all Azure RBAC roles that are available for assignment.

## SYNTAX

### RoleDefinitionNameParameterSet
```
Get-AzureRmRoleDefinition [[-Name] <String>] [-Scope <String>] [-AtScopeAndBelow]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### RoleDefinitionIdParameterSet
```
Get-AzureRmRoleDefinition -Id <Guid> [-Scope <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### RoleDefinitionCustomParameterSet
```
Get-AzureRmRoleDefinition [-Scope <String>] [-Custom] [-AtScopeAndBelow]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The **Get-AzureRmRoleDefinition** cmdlet gets all Azure role-based access control (RBAC) roles that are available for assignment.
To inspect individual operations that a role grants access to, review the Actions and NotActions properties of the role.

## EXAMPLES

### Example 1: Get a reader role definition


```
PS C:\> Get-AzureRmRoleDefinition -Name "Reader01"
```

This command gets the reader role definition from the reader named Reader01.

### Example 2: Get all RBAC role definitions


```
PS C:\> Get-AzureRmRoleDefinition
```

This command lists all RBAC role definitions.

## PARAMETERS

### -Name
Specifies the name of the role definition.
For instance, Reader, Contributor, Virtual Machine Contributor.

```yaml
Type: String
Parameter Sets: RoleDefinitionNameParameterSet
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scope
Specifies the scope of the role definition.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AtScopeAndBelow
Indicates that the cmdlet displays all role definitions.

```yaml
Type: SwitchParameter
Parameter Sets: RoleDefinitionNameParameterSet, RoleDefinitionCustomParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Id
Specifies the ID of the role definition.

```yaml
Type: Guid
Parameter Sets: RoleDefinitionIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Custom
Indicates that the cmdlet displays only the custom created roles in the directory.

```yaml
Type: SwitchParameter
Parameter Sets: RoleDefinitionCustomParameterSet
Aliases: 

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

[Get-AzureRmRoleAssignment](./Get-AzureRmRoleAssignment.md)

[New-AzureRmRoleAssignment](./New-AzureRmRoleAssignment.md)

[New-AzureRmRoleDefinition](./New-AzureRmRoleDefinition.md)

[Remove-AzureRmRoleDefinition](./Remove-AzureRmRoleDefinition.md)
