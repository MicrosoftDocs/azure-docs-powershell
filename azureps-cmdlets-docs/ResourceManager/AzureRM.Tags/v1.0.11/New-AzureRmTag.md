---
external help file: Microsoft.Azure.Commands.Tags.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=404172
schema: 2.0.0
---

# New-AzureRmTag

## SYNOPSIS
Creates a predefined Azure tag or adds values to an existing tag.

## SYNTAX

```
New-AzureRmTag [-Name] <String> [[-Value] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmTag** cmdlet creates a predefined Azure tag with an optional predefined value.
You can also use it to add additional values to existing predefined tags.
To create a predefined tag, enter a unique tag name.
To add a value to an existing predefined tag, specify the name of the existing tag and the new value.

This cmdlet returns an object that represents the new or modified tag with its values and the number of resources to which it has been applied.

You can define and apply tags in a single step, but predefined tags let you establish standard, consistent, predictable names and values for the tags in your subscription.
If the subscription includes any predefined tags, you cannot apply undefined tags or values to any resource or resource group in the subscription.

To apply a predefined tag to a resource or resource group, use the *Tag* parameter of the **New-AzureRMTag** cmdlet.
To search for resource groups with a specified tag name or name and value, use the *Tag* parameter of the **Get-AzureRmResourceGroup** cmdlet.

Every tag has a name.
The values are optional.
A predefined Azure tag can have multiple values, but when you apply the tag to a resource or resource group, you apply the tag name and only one of its values.
For example, you can create a predefined "Department" tag with a value for each department, such as "Finance", "Human Resources", and "IT".
When you apply the "Department" tag to a resource, you apply only one predefined value, such as "Finance".

## EXAMPLES

### Example 1: Create a predefined tag
```
PS C:\> New-AzureRmTag -Name "FY2015"
Name:   Department
Count:  0
Values:
        Name        Count
        =========   =====
        Finance     0
```

This command creates a predefined tag named "FY2015".
This tag has no values.
You can apply a tag with no values to a resource or resource group, or use the **New-AzureRmTag** cmdlet to add values to the tag.
You can also specify a value when you apply the tag to the resource or resource group.

### Example 2: Create a predefined tag with a value
```
PS C:\> New-AzureRmTag -Name "Department" -Value "Finance"
Name:   Department
Count:  0
Values:
        Name        Count
        =========   =====
        Finance     0
```

This command creates a predefined tag named "Department" with a value of "Finance".

### Example 3: Add a value to a predefined tag
```
PS C:\> New-AzureRmTag -Name "Department" -Value "Finance"
Name:   Department
Count:  0
Values:
        Name        Count
        =========   =====
        Finance     0

PS C:\> New-AzureRmTag -Name "Department" -Value "IT"
Name:   Department
Count:  0
Values:
        Name        Count
        =========   =====
        Finance     0
        IT          0
```

The first command creates a predefined tag named "Department" with the value "Finance".
The second command adds a value to the tag named "Department". Because the tag name exists, **New-AzureRmTag** adds the value "IT" to the existing tag instead of creating a new tag.

### Example 4: Create a predefined tag with a value and apply it to a resource group
```
PS C:\> New-AzureRmTag -Name "CostCenter" -Value "0001"
Name:   CostCenter
Count:  0
Values:
        Name        Count
        =========   =====
        0001        0

PS C:\> Set-AzureRmResourceGroup -Name "EngineerBlog" -Tag @{Name="CostCenter";Value="0001"}
Name:      EngineerBlog
Location:  East US
Resources:
    Name             Type                     Location
    ===============  =======================  ========
    EngineerBlog     Microsoft.Web/sites      West US
    EngSvr01         Microsoft.Sql/servers    West US
    EngDB02          Microsoft.Sql/databases  West US
Tags:
    Name         Value
    ==========   =====
    CostCenter   0001

PS C:\> Get-AzureRmTag -Name "CostCenter"
Name:   CostCenter
Count:  1
Values:
        Name        Count
        =========   =====
        0001        1

PS C:\> Get-AzureRmResourceGroup -Tag @{Name="CostCenter"}
Name:      EngineerBlog
Location:  East US
Resources:
    Name             Type                     Location
    ===============  =======================  ========
    EngineerBlog     Microsoft.Web/sites      West US
    EngSvr01         Microsoft.Sql/servers    West US
    EngDB02          Microsoft.Sql/databases  West US
Tags:
    Name         Value
    ==========   =====
    CostCenter   0001
```

The first command creates a tag named "CostCenter".
The **Set-AzureRmResourceGroup** cmdlet applies the tag to the resource group named "EngineerBlog".
The subsequent commands get the updated tag and resource group information.

## PARAMETERS

### -Name
Specifies the name of the tag.
To create a new predefined tag, enter a unique name.

To add a value to an existing tag, enter the name of the existing tag.
If an existing predefined tag has the specified name, **New-AzureRmTag** adds the specified value, if any, to the tag with that name instead of creating a new tag.

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

### -Value
Specifies a value of a tag.
Predefined tags can have multiple values, but you can enter only one value in each command.
This parameter is optional, because tags can have names without values.

```yaml
Type: String
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

### None

## OUTPUTS

### Microsoft.Azure.Commands.Tags.Model.PSTag

## NOTES

## RELATED LINKS

[Get-AzureRmResourceGroup](https://docs.microsoft.com/powershell/module/azurerm.resources/get-azurermresourcegroup)

[Get-AzureRmTag](./Get-AzureRmTag.md)

[Remove-AzureRmTag](./Remove-AzureRmTag.md)

[Set-AzureRmResourceGroup](https://docs.microsoft.com/powershell/module/azurerm.resources/set-azurermresourcegroup)
