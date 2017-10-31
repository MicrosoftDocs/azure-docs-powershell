---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393051
schema: 2.0.0
---

# New-AzureRmResource

## SYNOPSIS
Creates a new resource in a resource group

## SYNTAX

### The resource Id. (Default)
```
New-AzureRmResource [-Location <String>] [-Kind <String>] -Properties <PSObject> [-PlanObject <Hashtable>]
 [-SkuObject <Hashtable>] [-Tag <Hashtable[]>] [-IsFullObject] -ResourceId <String> [-ODataQuery <String>]
 [-Force] [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Resource that resides at the subscription level.
```
New-AzureRmResource [-Location <String>] [-Kind <String>] -Properties <PSObject> [-PlanObject <Hashtable>]
 [-SkuObject <Hashtable>] [-Tag <Hashtable[]>] [-IsFullObject] -ResourceName <String> -ResourceType <String>
 [-ExtensionResourceName <String>] [-ExtensionResourceType <String>] [-ODataQuery <String>]
 [-ResourceGroupName <String>] [-Force] [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Resource that resides at the tenant level.
```
New-AzureRmResource [-Location <String>] [-Kind <String>] -Properties <PSObject> [-PlanObject <Hashtable>]
 [-SkuObject <Hashtable>] [-Tag <Hashtable[]>] [-IsFullObject] -ResourceName <String> -ResourceType <String>
 [-ExtensionResourceName <String>] [-ExtensionResourceType <String>] [-ODataQuery <String>] [-TenantLevel]
 [-Force] [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The New-AzureRmResource cmdlet creates an Azure resource, such as a website, SQL Azure database server, or SQL Azure database, in a new or existing resource group.If a resource with the same name exists in the resource group, the cmdlet prompts for confirmation before replacing the existing resource.
To suppress the confirmation prompt, use the Force parameter.A resource is a user-managed Azure entity.
A resource group is a collection of resources that are deployed as a unit.
Every resource belongs to exactly one resource group.Typically, you use a template to create a resource group (New-AzureRmResourceGroup) and its resources.
Then, if necessary, you can use this cmdlet to add additional resources to it.

## EXAMPLES

### --------------------------  Example 1: Create a new web site  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResource -Name ContosoEngSite -Location "North Europe" -ResourceGroupName ContosoEngineering -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01 -PropertyObject @{"name" = "ContosoEngSite"; "siteMode" = "Limited"; "computeMode" = "Shared"} 
Name              : ContosoEngSite
ResourceGroupName : ContosoEngineering
ResourceType      : Microsoft.Web/sites
Location          : North Europe
Properties        : {[name, ContosoEngSite], [state, Running], [hostNames, 
                    System.Collections.Generic.List`1[System.Object]], [webSpace, 
                    ContosoEngineering-NorthEuropewebspace]...}
```

This command uses the New-AzureRmResource cmdlet to create the ContosoEngSite web site in the ContosoEngineering resource group.
If the ContosoEngineering resource group doesn't exist, New-AzureRmResource creates it.
If the ContosoEngineering resource group already has a resource named ContosoEngSite, the cmdlet prompt for confirmation before replacing it.

The command uses the Location parameter to place the new web in the "North Europe" data center, although the resource group and its resources are located in several different locations.The cmdlet returns a PSResource object that represents the new database.

### --------------------------  Example 2: Create a web site with property values  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>$WebsiteProperties = @{name = "ContosoWeb"; serverFarm = CS01; computeMode = "Shared"; siteMode = "Limited";}PS C:\>New-AzureRmResource -Name ContosoWeb -ResouceGroupName CRG01 -ResourceType 'Microsoft.Web/sites' -Location "South Central US" -ApiVersion 2014-04-01 -PropertyObject $WebsiteProperties
Name              : ContosoWeb
ResourceGroupName : ContosoEngineering
ResourceType      : Microsoft.Web/sites
Location          : South Central US
Properties        : {[name, ContosoWeb], [state, Running], [hostNames, 
                    System.Collections.Generic.List`1[System.Object]], [webSpace, 
                   CRG01-Southcentralwebspace]...}
```

These commands create the ContosoWeb Azure website in the CRG01 resource group.

The first command creates a hash table of web site properties and saves it in the $WebsiteProperties variable.
To find the properties that you can set for an Azure web site, use a gallery template, such as the ones that the Get-AzureRmResourceGroupGalleryTemplate cmdlet return.The second command uses the New-AzureRmResource cmdlet to create the web site.
The value of the PropertyObject parameter is the hash table in the $WebsiteProperties variable.

### --------------------------  Example 3: Add a website to a resource group  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResourceGroup -Name ContosoPortal -Location "West US" -GalleryTemplateIdentity WordPress.WordPress.0.1.0-preview1 -TemplateParameterFile ".\WordPressParameters.json"


PS C:\>New-AzureRmResource -Name sqldb03 -ResourceType "Microsoft.Sql/servers/databases" -ResourceGroup ContosoPortal -Location "West US" -ParentResource "Microsoft.Sql/servers/ContosoServer01" -PropertyObject @{Edition = "Enterprise"; MaxSizeGB = 100}
```

This example shows a typical use of this cmdlet.
The first command uses the New-AzureRmResourceGroup cmdlet to create the ContosoPortal resource group.
The command uses the WordPress gallery template (Get-AzureRmResourceGroupGalleryTemplate) and a JSON file, WordPressParameters.json, to specify values for the template-specific parameters, such as the name and location of the database, a name for the hosting plan, and web deployment credentials.

The second command uses the New-AzureRmResource cmdlet to add an additional database to the ContosoPortal resource group.
The command uses the PropertyObject parameter to specify a hash table of values for the Edition and MaxSizeGB properties of the new database.
For the other databases in the resource group, these values were specified in the PortalParameters.rgcfg resource group configuration file.

### --------------------------  Example 4: Create a resource group with  tags  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResource -Name ContosoEngSite -Location "North Europe" -ResourceGroupName ContosoEngineering -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01 -Tag @{Name="Status";Value="Approved"},@{Name="New"}
```

This command creates a new website and applies two tags to it.
The command uses the Tag parameter to apply a "Status" tag with a value of "Approved" and a tag named "New" with no value.

## PARAMETERS

### -ApiVersion
Specifies the API version that is supported by the resource provider.
This parameter is required.

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

### -ExtensionResourceName
The extension resource name.
e.g.
to specify a database MyServer/MyDatabase.

```yaml
Type: String
Parameter Sets: Resource that resides at the subscription level., Resource that resides at the tenant level.
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExtensionResourceType
The extension resource type.
e.g.
Microsoft.Sql/Servers/Databases.

```yaml
Type: String
Parameter Sets: Resource that resides at the subscription level., Resource that resides at the tenant level.
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Overwrites an existing resource group without warning.
This parameter suppresses the confirmation prompt that New-AzureRmResource displays by default when the resource group already contains a resource with the same resource name.

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

### -IsFullObject
When set indicates that the full object is passed in to the -PropertyObject parameter.

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

### -Kind
The resource kind.

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

### -Location
Specifies the location of the resource.
This parameter is required.
Enter an Azure data center location, such as "West US" or "Southeast Asia".You can place a resource in any location that supports resources of that type.
The resource does not have to be in the same location your Azure subscription or the same location as its resource group.
Resource groups can contain resources from different locations.
To determine which locations support each resource type, use the Get-AzureRmResourceProvider with the ProviderNamespace parameter cmdlet.

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

### -ODataQuery
An OData style filter which will be appended to the request in addition to any other filters.

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

### -PlanObject
A hash table which represents resource plan properties.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Properties
A hash table which represents resource properties.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: PropertyObject

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the resource group for this resource.
This parameter is required.
Enter the name of a new or existing resource group.
If the resource group doesn't exist, this cmdlet creates it for you.A resource group is a collection of resources that are deployed as a unit.
Every resource belongs to exactly one resource group.

```yaml
Type: String
Parameter Sets: Resource that resides at the subscription level.
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
The fully qualified resource Id, including the subscription.
e.g.
/subscriptions/{subscriptionId}/providers/Microsoft.Sql/servers/myServer/databases/myDatabase

```yaml
Type: String
Parameter Sets: The resource Id.
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceName
The resource name.
e.g.
to specify a database MyServer/MyDatabase.

```yaml
Type: String
Parameter Sets: Resource that resides at the subscription level., Resource that resides at the tenant level.
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceType
Enter the type of the resource that you are creating, such as "Microsoft.Web/sites" or " Microsoft.Sql/servers/databases".
This parameter is required and its value is case-sensitive.
Wildcards are not permitted.

```yaml
Type: String
Parameter Sets: Resource that resides at the subscription level., Resource that resides at the tenant level.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuObject
A hash table which represents sku properties.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Applies the specified tags to the new resource.
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -TenantLevel
Indicates that this is a tenant level operation.

```yaml
Type: SwitchParameter
Parameter Sets: Resource that resides at the tenant level.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.Azure.Commands.ResourceManagement.Models.PSResource

## NOTES

## RELATED LINKS

