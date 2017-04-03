---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 8300B143-E322-419E-BC98-DBA56DD90A59
online version: 
schema: 2.0.0
---

# New-AzureRmRoleDefinition

## SYNOPSIS
Creates a custom role in Azure RBAC.


## SYNTAX

### InputFileParameterSet
```
New-AzureRmRoleDefinition [-InputFile] <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### RoleDefinitionParameterSet
```
New-AzureRmRoleDefinition [-Role] <PSRoleDefinition> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

## DESCRIPTION
The **New-AzureRmRoleDefinition** cmdlet creates a custom role in Azure Role-Based Access Control.
Provide a role definition as an input to the command as a JSON file or a **PSRoleDefinition** object.

The input role definition MUST contain the following properties:

- DisplayName: the name of the custom role

- Description: a short description of the role that summarizes the access that the role grants.

- Actions: the set of operations to which the custom role grants access.
Use Get-AzureRmProviderOperations to get the operation for Azure resource providers that can be secured using Azure RBAC.
Following are some valid operation strings:
 - "*/read" grants access to read operations of all Azure resource providers.
 - "Microsoft.Network/*/read" grants access to read operations for all resource types in the Microsoft.Network resource provider of Azure.
 - "Microsoft.Compute/virtualMachines/*" grants access to all operations of virtual machines and its child resource types.

- AssignableScopes: the set of scopes (Azure subscriptions or resource groups) in which the custom role will be available for assignment.
Using the *AssignableScopes* parameter you can make the custom role available for assignment in only the subscriptions or resource groups that need it, and not clutter the user experience for the rest of the subscriptions or resource groups.
Following are some valid assignable scopes:
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e", "/subscriptions/e91d47c4-76f3-4271-a796-21b4ecfe3624": makes the role available for assignment in two subscriptions.
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e": makes the role available for assignment in a single subscription.
 - "/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e/resourceGroups/Network": makes the role available for assignment only in the Network resource group.

The input role definition MAY contain the following properties:

- NotActions: the set of operations that must be excluded from the Actions to determine the effective actions for the custom role.
If there is a specific operation that you do not wish to grant access to in a custom role, it is convenient to use NotActions to exclude it, rather than specifying all operations other than that specific operation in Actions.

If a user is assigned a role that specifies an operation in NotActions and also assigned another role grants access to the same operation - the user will be able to perform that operation.
NotActions is not a deny rule - it is simply a convenient way to create a set of allowed operations when specific operations need to be excluded.

Following is a sample json role definition that can be provided as input
        {
        "Name": "Contoso On-call",
        "Description": "Can monitor compute, network and storage, and restart virtual machines",
        "Actions": \[
        "Microsoft.Compute/*/read",
        "Microsoft.Compute/virtualMachines/start/action",
        "Microsoft.Compute/virtualMachines/restart/action",
        "Microsoft.Compute/virtualMachines/downloadRemoteDesktopConnectionFile/action",
        "Microsoft.Network/*/read",
        "Microsoft.Storage/*/read",
        "Microsoft.Authorization/*/read",
        "Microsoft.Resources/subscriptions/resourceGroups/read",
        "Microsoft.Resources/subscriptions/resourceGroups/resources/read",
        "Microsoft.Insights/alertRules/*",
        "Microsoft.Support/*"
        \],
        "AssignableScopes": \["/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx","/subscriptions/yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy"\]
        }
        
You must provide either a JSON role definition file or a **PSRoleDefinition** object as input.
First, use the [Get-AzureRmRoleDefinition](./Get-AzureRmRoleDefinition.md) command to generate a baseline role definition object.
Then, modify its properties as required.
Finally, use this command to create a custom role using role definition.

## EXAMPLES

### Example 1:  Create a role definition file using PSRoleDefinitionObject


```
PS C:\> $Role = Get-AzureRmRoleDefinition -Name "Virtual Machine Contributor"
          PS C:\> $Role.Id = $null
          PS C:\> $Role.Name = "Virtual Machine Operator"
          PS C:\> $Role.Description = "Can monitor, start, and restart virtual machines."
          PS C:\> $Role.Actions.RemoveRange(0,$Role.Actions.Count)
          PS C:\> $Role.Actions.Add("Microsoft.Compute/*/read")
          PS C:\> $Role.Actions.Add("Microsoft.Compute/virtualMachines/start/action")
          PS C:\> $Role.Actions.Add("Microsoft.Compute/virtualMachines/restart/action")
          PS C:\> $Role.Actions.Add("Microsoft.Compute/virtualMachines/downloadRemoteDesktopConnectionFile/action")
          PS C:\> $Role.Actions.Add("Microsoft.Network/*/read")
          PS C:\> $Role.Actions.Add("Microsoft.Storage/*/read")
          PS C:\> $Role.Actions.Add("Microsoft.Authorization/*/read")
          PS C:\> $Role.Actions.Add("Microsoft.Resources/subscriptions/resourceGroups/read")
          PS C:\> $Role.Actions.Add("Microsoft.Resources/subscriptions/resourceGroups/resources/read")
          PS C:\> $Role.Actions.Add("Microsoft.Insights/alertRules/*")
          PS C:\> $Role.Actions.Add("Microsoft.Support/*")
          PS C:\> $Role.AssignableScopes.Remove("/") | Out-Null
          PS C:\> $Role.AssignableScopes.Add("/subscriptions/c276fc76-9cd4-44c9-99a7-4fd71546436e")

          PS C:\> New-AzureRmRoleDefinition -Role $Role
```

### Example 2: Create a role definition using JSON file  


```
PS C:\> New-AzureRmRoleDefinition -InputFile C:\Temp\roleDefinition.json
```

## PARAMETERS

### -InputFile
File name containing a single JSON role definition.

```yaml
Type: String
Parameter Sets: InputFileParameterSet
Aliases: 

Required: True
Position: 0
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

### -Role
Specifies a role definition object.

```yaml
Type: PSRoleDefinition
Parameter Sets: RoleDefinitionParameterSet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[Get-AzureRmRoleDefinition](./Get-AzureRmRoleDefinition.md)

[Remove-AzureRmRoleDefinition](./Remove-AzureRmRoleDefinition.md)

[Set-AzureRmRoleDefinition](./Set-AzureRmRoleDefinition.md)

[Get-AzureRmProviderOperation](./Get-AzureRmProviderOperation.md)
