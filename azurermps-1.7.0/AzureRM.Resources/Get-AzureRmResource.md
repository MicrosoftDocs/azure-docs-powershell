---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393050
schema: 2.0.0
---

# Get-AzureRmResource

## SYNOPSIS
Gets Azure resources

## SYNTAX

### The list all resources parameter set. (Default)
```
Get-AzureRmResource [-ExpandProperties] [-ODataQuery <String>] [-ApiVersion <String>] [-Pre]
 [<CommonParameters>]
```

### Get a single resource by its Id.
```
Get-AzureRmResource -ResourceId <String> [-ExpandProperties] [-ODataQuery <String>] [-ApiVersion <String>]
 [-Pre] [<CommonParameters>]
```

### Get a resource by name and type.
```
Get-AzureRmResource [-ResourceName <String>] [-ResourceType <String>] [-ExtensionResourceName <String>]
 [-ExtensionResourceType <String>] [-ExpandProperties] [-IsCollection] [-ODataQuery <String>]
 [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Lists the resources based on the specified scope at the tenant level.
```
Get-AzureRmResource [-ResourceName <String>] [-ResourceType <String>] [-ExtensionResourceName <String>]
 [-ExtensionResourceType <String>] [-ExpandProperties] [-IsCollection] [-Top <Int32>] [-ODataQuery <String>]
 [-TenantLevel] [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Get resource by name, group and type
```
Get-AzureRmResource -ResourceName <String> -ResourceType <String> [-ExtensionResourceName <String>]
 [-ExtensionResourceType <String>] [-ExpandProperties] [-ODataQuery <String>] -ResourceGroupName <String>
 [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Get a single resource at the tenant level.
```
Get-AzureRmResource -ResourceName <String> -ResourceType <String> [-ExtensionResourceName <String>]
 [-ExtensionResourceType <String>] [-ExpandProperties] [-IsCollection] [-ODataQuery <String>] [-TenantLevel]
 [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Get resource by name and group
```
Get-AzureRmResource [-ResourceName <String>] [-ExtensionResourceName <String>]
 [-ExtensionResourceType <String>] [-ExpandProperties] [-IsCollection] [-ODataQuery <String>]
 [-ResourceGroupName <String>] [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Get resource collection
```
Get-AzureRmResource [-ResourceType <String>] [-ExtensionResourceType <String>] [-ExpandProperties]
 [-IsCollection] [-ODataQuery <String>] [-ResourceGroupName <String>] [-ApiVersion <String>] [-Pre]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureRmResource cmdlet gets the Azure resources in the subscription.
By default, it gets all resources in the subscription, but you can use the parameters in the cmdlet to filter the results.An Azure resource is a user-managed Azure entity, such as a database server, database, or website.
Every Azure resource is associated with a resource group, which is a collection of resources that are deployed as a unit.

If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Example 1: Get all resources  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource
Name              : HostingFarm1
ResourceGroupName : ContosoHosting
ResourceType      : Microsoft.Web/serverFarms
Location          : southcentralus
ParentResource        : 


Name              : ContosoDev
ResourceGroupName : ContosoLabsRG
ResourceType      : Microsoft.Web/sites
Location          : southcentralus
ParentResource        : 
                       
...
```

This commands gets all Azure resources in the subscription.

### --------------------------  Example 2: Get resources by resource group  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource -ResourceGroupName ContosoRG01
                       
Name              : Default1
ResourceGroupName : ContosoLabsRG
ResourceType      : Microsoft.Web/serverFarms
Location          : northeurope
ParentResource        : 


Name              : ContosoLabWeb
ResourceGroupName : ContosoLabsRG
ResourceType      : Microsoft.Web/sites
Location          : northeurope
ParentResource        :
```

This commands gets all Azure resources in the ContosoRG01 resource group.

### --------------------------  Example 3: Get resources by resource type  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource | Group-Object ResourceType

Count Name                      Group
----- ----                      -----
    6 microsoft.insights/ale... {@{Name=ServerErrors-goorg016
    6 microsoft.insights/aut... {@{Name=Default23-foorg016; R
    6 microsoft.insights/com... {@{Name=goorg016ws; ResourceG
    1 Microsoft.Web/serverFarms {@{Name=Default1; ResourceGro
    6 Microsoft.Web/sites       {@{Name=utr2520; ResourceGrou

PS C:\>Get-AzureRmResource -ResourceType Microsoft.Web/serverFarms
Name              : Default1
ResourceGroupName : ContosoLabsRG
ResourceType      : Microsoft.Web/serverFarms
Location          : southcentralus
ParentResource        : 


Name              : Default1
ResourceGroupName : ContosoRG01
ResourceType      : Microsoft.Web/serverFarms
Location          : northeurope
ParentResource        : 


Name              : Default1
ResourceGroupName : ContosoEngineering
ResourceType      : Microsoft.Web/serverFarms
Location          : southcentralus
ParentResource        : 


Name              : Default2
ResourceGroupName : ContosoEngineering
ResourceType      : Microsoft.Web/serverFarms
Location          : southcentralus
ParentResource        :
```

These commands get all resources with a specified resource type.

The first command finds the types of resources in the subscription.
It uses the Get-AzureRmResource cmdlet to get all resources and Group-Object cmdlet to group the objects by resource type.
The output shows that there are server farms and web sites in the subscription.The second command uses the ResourceType parameter of Get-AzureRmResource to get all server farms in the subscription.

### --------------------------  Example 4: Get a resource by name  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource -Name ContosoLabWeb -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2014-04-01
Name              : ContosoLabWeb
ResourceGroupName : ContosoLabsRG
ResourceType      : Microsoft.Web/sites
ParentResource    : 
Location          : North Europe
Properties        : 
                    {[name, ContosoLabWeb], [state, Running], [hostNames, 
                     System.Collections.Generic.List`1[System.Object]], [webSpace,
                     ContosoLabsRG-NorthEuropewebspace]...} 
Tags              :
```

This commands gets the "ContosoLabWeb" web site resource.
When you use the Name parameter to get a particular resource, the ResourceGroupName, ResourceType, and APIVersion parameters are required.

You can also use the Where-Object cmdlet to select a resource.
For example: Get-AzureRmResource | Where-Object Name -eq "ConsotoLabWeb"

### --------------------------  Example 5: Get a resource by its tag  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource -Tag @{Name="Department";Value="IT"}
```

This command gets resources that have a tag named "Department with a value of "IT".

### --------------------------  Example 6: Get all tags of a resource  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource -Name ContosoLabWeb -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2014-04-01

PS C:\>(Get-AzureRmResource -Name ContosoLabWeb -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2014-04-01).Tags


Tags: 

      Name        Value
      ====        ======
      Department  IT
      Status      Approved
      FY2016
```

These commands get all tags of the ContosoWeb  resource. 
The first command gets the resource by name with all of its properties.
The second command, which uses the Tags property of the output object, gets only the tags.

## PARAMETERS

### -ApiVersion
Specifies the API version that is supported by the resource provider.
This parameter is required when you use the Name parameter.

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

### -ExpandProperties
When specified, expands the properties of the resource.

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

### -ExtensionResourceName
The extension resource name.
e.g.
to specify a database MyServer/MyDatabase.

```yaml
Type: String
Parameter Sets: Get a resource by name and type., Lists the resources based on the specified scope at the tenant level., Get resource by name, group and type, Get a single resource at the tenant level., Get resource by name and group
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
Parameter Sets: Get a resource by name and type., Lists the resources based on the specified scope at the tenant level., Get resource by name, group and type, Get a single resource at the tenant level., Get resource by name and group
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get resource collection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsCollection
When specified, ensures that the query is run against a collection instead of a resource.

```yaml
Type: SwitchParameter
Parameter Sets: Get a resource by name and type., Lists the resources based on the specified scope at the tenant level., Get a single resource at the tenant level., Get resource by name and group, Get resource collection
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

### -ResourceGroupName
Gets only resources in the specified resource group.
Wildcards are not permitted.
This parameter is required only when you are selecting resources by name.
By default, Get-AzureRmResource gets all resources in the subscription.

```yaml
Type: String
Parameter Sets: Get resource by name, group and type
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get resource by name and group
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get resource collection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
The resource's Id.

```yaml
Type: String
Parameter Sets: Get a single resource by its Id.
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
Parameter Sets: Get a resource by name and type., Lists the resources based on the specified scope at the tenant level., Get resource by name and group
Aliases: Name

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get resource by name, group and type, Get a single resource at the tenant level.
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceType
Gets only resources of the specified resource type.
Wildcards are not permitted.
This parameter is required only when you are selecting resources by name.
By default, GetAzureResource gets all resources in the subscription.

```yaml
Type: String
Parameter Sets: Get a resource by name and type., Lists the resources based on the specified scope at the tenant level.
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get resource by name, group and type, Get a single resource at the tenant level.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get resource collection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantLevel
Indicates that this is a tenant level operation.

```yaml
Type: SwitchParameter
Parameter Sets: Lists the resources based on the specified scope at the tenant level., Get a single resource at the tenant level.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
The number of resources to retrieve.

```yaml
Type: Int32
Parameter Sets: Lists the resources based on the specified scope at the tenant level.
Aliases: 

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
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

