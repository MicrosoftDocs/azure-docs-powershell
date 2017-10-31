---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-AzureRmTag

## SYNOPSIS
Deletes predefined Azure tags or values.

## SYNTAX

```
Remove-AzureRmTag [-Name] <String> [[-Value] <String[]>] [-Force] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmTag** cmdlet deletes predefined Azure tags or values from your subscription.
To delete particular values from a predefined tag, use the *Value* parameter.
By default, **Remove-AzureRmTag** deletes the specified tag and all of its values. You cannot delete a tag or value that is currently applied to a resource or resource group.

Before using **Remove-AzureRmTag**, use the *Tag* parameter of the **Set-AzureRmResourceGroup** cmdlet to delete the tag or values from the resource or resource group.

You can define and apply tags in a single step, but predefined tags let you establish standard, consistent, predictable names and values for the tags in your subscription.
If the subscription includes any predefined tags, you cannot apply undefined tags or values to any resource or resource group in the subscription.

## EXAMPLES

### Example 1: Delete a predefined tag
```
PS C:\> Remove-AzureRmTag -Name "Department"
```

This command deletes the predefined tag named "Department" and all of its resources.
If the tag has been applied to any resources or resource groups, the command fails.

### Example 2: Delete a value from a predefined tag
```
PS C:\> Remove-AzureRmTag -Name "Department" -Value "HumanResources" -PassThru
Name:   Department
Count:  14
Values:
        Name        Count
        =========   =====
        Finance        2
        IT            12
```

This command deletes the "HumanResources" value from the predefined tag named "Department".
It does not delete the tag.
If the value has been applied to any resources or resource groups, the command fails.

## PARAMETERS

### -Force
Indicates whether to force the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the tag to be deleted.
By default, **Remove-AzureRmTag** removes the specified tag and all of its values.
To delete selected values, but not delete the tag, use the *Value* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates whether to return an object that represents the deleted tag or the resulting tag with deleted value.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Specifies the values to be deleted from the predefined tag. The tag is not deleted.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
### System.String[]

## OUTPUTS

### Microsoft.Azure.Commands.Tags.Model.PSTag

## NOTES

## RELATED LINKS

[Get-AzureRMTag](./Get-AzureRmTag.md)

[New-AzureRMTag](./New-AzureRmTag.md)

[Set-AzureRmResourceGroup](https://docs.microsoft.com/powershell/module/azurerm.resources/set-azurermresourcegroup)
