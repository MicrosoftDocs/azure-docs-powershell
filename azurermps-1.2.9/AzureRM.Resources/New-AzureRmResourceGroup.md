---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393048
schema: 2.0.0
---

# New-AzureRmResourceGroup

## SYNOPSIS
Creates an Azure resource group and its resources

## SYNTAX

```
New-AzureRmResourceGroup -Name <String> -Location <String> [-Tag <Hashtable[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The New-AzureRmResourceGroup cmdlet creates an Azure resource group and its resources and returns an object that represents the resource group.Use this cmdlet to create a new resource group.
To add a deployment to an existing resource group, use the New-AzureRmResourceGroupDeployment cmdlet.
To add a resource to an existing resource group, use the New-AzureRmResource cmdlet.An Azure resource is a user-managed Azure entity, such as a database server, database, or web site.
An Azure resource group is a collection of Azure resources that are deployed as a unit.You can create a resource group with just a name and location, and then use the New-AzureRmResource cmdlet to create resources and add them to the resource group.
However, typically, you use a resource group template, which is a JSON-based model of a resource group for a complex cloud-based service, such as a web portal.
You can find many templates in the Azure template gallery (Get-AzureRmResourceGroupGalleryTemplate) and you can create your own templates.To find a gallery template, use the Get-AzureRmResourceGroupGalleryTemplate template cmdlet.
To use a gallery template, use the GalleryTemplateIdentity parameter of New-AzureRmResourceGroup to specify the template identity.
Or, use the Save-AzureRmResourceGalleryTemplate cmdlet to save the gallery template as a JSON file, and then use the TemplateFile or TemplateUri parameters to provide the name and location of the file.You can also create a custom resource group template, either by typing in a text file  or by editing a gallery template.
To use a custom template to create a resource group, use TemplateFile or TemplateUri parameters to supply the location and file name.The template includes parameters (placeholders) for configurable property values, likes names and sizes.
To specify values for the template parameters, use a JSON-formatted parameter file (TemplateParameterFile parameter) or a hash table of parameter names and values (TemplateParameterObject parameter).
Or, you can use the template parameters that are added to the command dynamically as soon as you specify a template.
To use the dynamic parameters, just type them in the command, or type a minus sign to indicate a parameter name (-) and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.
Template parameter values that you specify at the command line take precedence over template parameter values in a template parameter object or file.

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

### -Tag
Applies the specified tags to the new resource group.
Enter new tags or predefined tags that you created by using the New-AzureRmTag cmdlet.A "tag" is a name-value pair that you can apply to resources and resource groups.
Use tags to categorize your resources, such as by department or cost center, or to track notes or comments about the resources.
After you assign tags to resources, you can use the Tag parameters of Get-AzureRmResource and Get-AzureRmResourceGroup to search for resources and groups by tag name or name and value.Every tag must have a Name key.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManagement.Models.PSResourceGroup

## NOTES

## RELATED LINKS

