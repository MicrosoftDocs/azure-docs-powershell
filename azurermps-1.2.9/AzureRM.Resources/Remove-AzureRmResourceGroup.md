---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393049
schema: 2.0.0
---

# Remove-AzureRmResourceGroup

## SYNOPSIS
Deletes a resource group.

## SYNTAX

### Lists the resource group based in the name. (Default)
```
Remove-AzureRmResourceGroup [-Name] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Lists the resource group based in the Id.
```
Remove-AzureRmResourceGroup [-Id] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Remove-AzureRmResourceGroup cmdlet deletes a resource group and its resources from your subscription.
By default, Remove-AzureRmResourceGroup prompts you for confirmation.
To suppress the prompt, use the Force parameter.To delete a resource, but leave the resource group, use the Remove-AzureRmResource cmdlet.

## EXAMPLES

### --------------------------  Example 1: Remove a resource group  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Remove-AzureRmResourceGroup -Name -ContosoRG01
Confirm

Are you sure you want to remove resource group 'ContosoRG01'

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This command removes the ContosoRG01 resource group from the subscription.
The cmdlet prompts for confirmation and does not return any output by default.

### --------------------------  Example 2: Use the Force parameter  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup -Name ContosoRG01 | Remove-AzureRmResourceGroup -Verbose -Force
VERBOSE: Performing the operation "Removing resource group ..." on target "ContosoRG01".
```

This command deletes the ContosoRG01 resource group from the subscription.
It uses the Get-AzureRmResourceGroup cmdlet to get the resource group and pipes the resource group (by name) to the Remove-AzureRmResourceGroup cmdlet.
The Remove-AzureRmResourceGroup command uses the Verbose common parameter to get status information about the operation and the Force parameter to suppress the confirmation prompt.

### --------------------------  Example 3: Remove all resource groups  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup | Remove-AzureRmResourceGroup -PassThru

Confirm

Are you sure you want to remove resource group 'ContosoRG01'

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

True



Confirm

Are you sure you want to remove resource group 'ContosoRG02'

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

True
```

This command deletes all resource groups in the subscription.
To get all resource groups, it uses a Get-AzureRmResourceGroup command with no parameters.
Then, it pipes the resource groups to the Remove-AzureRmResourceGroup cmdlet.
The Remove-AzureRmResourceGroup command uses the Passthru parameter.
As a result, the cmdlet returns a value of $True for each operation that succeeds.

## PARAMETERS

### -Force
Suppresses the confirmation prompt.
By default, Remove-AzureRmResource prompts you to confirm before deleting a resource group.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the Id of resource groups to delete.
This parameter is required.
Wildcards are not permitted.

```yaml
Type: String
Parameter Sets: Lists the resource group based in the Id.
Aliases: ResourceGroupId, ResourceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the names of resource groups to delete.
This parameter is required.
Wildcards are not permitted.Use -Name or its alias, -ResourceGroupName.

```yaml
Type: String
Parameter Sets: Lists the resource group based in the name.
Aliases: ResourceGroupName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

