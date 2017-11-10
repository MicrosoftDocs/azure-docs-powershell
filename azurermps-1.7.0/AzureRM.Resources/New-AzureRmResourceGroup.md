---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393048
schema: 2.0.0
---

# New-AzureRmResourceGroup

## SYNOPSIS
Creates an Azure resource group

## SYNTAX

```
New-AzureRmResourceGroup -Name <String> -Location <String> [-Tag <Hashtable[]>] [-Force] [-ApiVersion <String>]
 [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmResourceGroup cmdlet creates an Azure resource group and returns an object that represents the resource group.

If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Example 1: Create an empty resource group  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResourceGroup -Name RG1 -Location "South Central US"
          ResourceGroupName : RG1
          Location          : southcentralus
          ProvisioningState : Succeeded
          Resources
```

This command creates a resource group that has no resources.
You can use the New-AzureRmResource or New-AzureRmResourceGroupDeployment cmdlets to add resources and deployments to this resource group.

### --------------------------  Example 2: Create a resource group with tags  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResourceGroup -Name RG1 -Location "South Central US" -Tag @{Name="Empty"}, @{Name="Department";Value="Marketing"}
```

This command creates a new empty resource group.
This command is the same as the command in Example 1, except that it assigns tags to the resource group.
The first tag, named "Empty," could be used to identify resource groups that have no resources.
The second tag is named "Department" and has a value of "Marketing".
You can use a tag like this one to categorize resource groups for administration or budgeting.

## PARAMETERS

### -ApiVersion
When set, indicates the version of the resource provider API to use.
If not specified, the API version is automatically determined as the latest available.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Suppresses the confirmation prompt and overwrites an existing resource group with the same name.
By default, New-AzureRmResourceGroup prompts for confirmation before replacing an existing resource group.

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

### -Location
Specifies the location of the resource group.
This parameter is required.
Enter an Azure data center location, such as "West US" or "Southeast Asia".You can place a resource group in any location.
The resource group does not have to be in the same location your Azure subscription or the same location as its resources.
Resource groups can contain resources from different locations.
To determine which location support each resource type, use the Get-AzureRmResourceProvider with the ProviderNamespace parameter cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the resource group.
This parameter is required.
The resource name must be unique in the subscription.You can use -Name or its alias, -ResourceGroupName.If a resource group with that name already exists, the command prompts you for confirmation before replacing the existing resource group.
To suppress the confirmation prompt, use the Force parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pre
When set, indicates that the cmdlet should use pre-release API versions when automatically determining which version to use.

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

### -Tag
Applies the specified tags to the new resource group.
Enter new tags or predefined tags that you created by using the New-AzureRmTag cmdlet.A "tag" is a name-value pair that you can apply to resources and resource groups.
Use tags to categorize your resources, such as by department or cost center, or to track notes or comments about the resources.
After you assign tags to resources, you can use the Tag parameters of Find-AzureRmResource and Find-AzureRmResourceGroup to search for resources and groups by tag name or name and value.Every tag must have a Name key.
It can also have an optional Value key with one value.
To specify a new tag, use a hash table, such as @{Name="FY2015"} or @{Name="Department";Value="IT"}.
To specify multiple tags, use commas to separate the hash tables, such as  -Tag @{Name="FY2015"}, @{Name="Department";Value="IT"}.
To get your predefined tags, use the Get-AzureRmTag cmdlet.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
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

### None

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManagement.Models.PSResourceGroup

## NOTES

## RELATED LINKS

