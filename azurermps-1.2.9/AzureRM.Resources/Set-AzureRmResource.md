---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393461
schema: 2.0.0
---

# Set-AzureRmResource

## SYNOPSIS
Changes the properties of an Azure resource.

## SYNTAX

### The resource Id. (Default)
```
Set-AzureRmResource [-Kind <String>] [-Properties <PSObject>] [-Plan <Hashtable>] [-Sku <Hashtable>]
 [-Tag <Hashtable[]>] [-UsePatchSemantics] -ResourceId <String> [-ODataQuery <String>] [-Force]
 [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Resource that resides at the subscription level.
```
Set-AzureRmResource [-Kind <String>] [-Properties <PSObject>] [-Plan <Hashtable>] [-Sku <Hashtable>]
 [-Tag <Hashtable[]>] [-UsePatchSemantics] -ResourceName <String> -ResourceType <String>
 [-ExtensionResourceName <String>] [-ExtensionResourceType <String>] [-ODataQuery <String>]
 [-ResourceGroupName <String>] [-Force] [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Resource that resides at the tenant level.
```
Set-AzureRmResource [-Kind <String>] [-Properties <PSObject>] [-Plan <Hashtable>] [-Sku <Hashtable>]
 [-Tag <Hashtable[]>] [-UsePatchSemantics] -ResourceName <String> -ResourceType <String>
 [-ExtensionResourceName <String>] [-ExtensionResourceType <String>] [-ODataQuery <String>] [-TenantLevel]
 [-Force] [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Set-AzureRmResource cmdlet changes the properties of an Azure resource.
To use the cmdlet, use the Name, ResourceGroupName, ResourceGroupType, and ParentResource parameters to identify the resource, and the PropertyObject parameter to specify the new property names and values.If the command succeeds, it returns the resource with the new properties and values.An Azure resource is a user-managed entity, such as an Azure Website or Azure SQL Database.
Some resources have properties, which are user-configured values, like sizes and operational modes.
You can specify these values when you create the resource, such as by using the New-AzureRmResource, New-AzureRmResourceGroup, or New-AzureRmResourceGroupDeployment cmdlets.
And, you can change the properties by using this cmdlet.To get the properties of a resource, use the Get-AzureRmResource cmdlet to get the resource.
Then use the dot method to get the Properties property collection and a particular named property.
For example, to get the siteMode property of an object, type (Get-AzureRmResource -Name MyWebSite -ResourceGroupName RG -ResourceType Microsoft.Web/sites -ApiVersion 2014-04-01).Properties.siteMode

## EXAMPLES

### --------------------------  Example 1: Change the properties of a resource  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> The first command uses the Get-AzureRmResource cmdlet to get the ContosoLabWeb2 web site. The command saves the resource in the $r variable.
PS C:\>$r = Get-AzureRmResource -Name ContosoLabWeb2 -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01

The second command saves the Properties property (and its properties) of the resource in the $p variable. The Properties object is a Dictionary, but because it is convertible to a hash table, you can use it as the value of the PropertyObject parameter of Set-AzureRmResource without casting.
PS C:\>$p = $r.Properties

The third command displays the properties in the $p variable.
PS C:\>$pName                           Value----                           -----name                           ContosoLabWeb2storageRecoveryDefaultState    RunningavailabilityState              0trafficManagerHostNamesrepositorySiteName             ContosoLabWeb2runtimeAvailabilityState       0siteMode                       LimitedruntimeADUserlastModifiedTimeUtc            3/25/2014 6:00:04 PMusageState                     0hostNames                      {contosolabweb2.antares-int.windows-int.net}adminEnabled                   TruehostNameSslStates              {System.Collections.Generic.Dictionary`2[System.String,System.Object], System.Collect...runtimeADUserDomainenabled                        TruedeploymentId                   ContosoLabWeb2selfLink                       https://antpreview2.api.admin-antares-int.windows-int.net:454/20130801/websystems/web...computeMode                    0webSpace                       ContosoLabsRG-NorthEuropewebspacecsrs                           {}siteConfigintegratedSqlAuthEnabled       Falsestate                          RunningruntimeADUserPasswordserverFarm                     Default1sslCertificates                {}cerscontentAvailabilityState       0enabledHostNames               {contosolabweb2.antares-int.windows-int.net, contosolabweb2.scm.antares-int.windows-i...windowsAuthEnabled             0ownersiteProperties                 {[metadata, ], [properties, System.Collections.Generic.List`1[System.Object]], [appSe...sku                            Free

The fourth command is actually a series of commands (delimited by semi-colons) that change the values of the properties in the $p variable.
PS C:\>$p.siteMode = "Basic"; $p.sku = "Basic"; $p.computeMode = "Dedicated"; $p.serverFarm = "Default2"

The fifth command uses the Set-AzureRmResource cmdlet to change the change the properties of the ContosoLabWeb2 web site. The value of the PropertyObject parameter is the $p variable that contains the Properties object and the new values. The command saves the output (the updated resource) in the $r2 variable.
PS C:\>$r2 = Set-AzureRmResource -Name ContosoLabWeb2 -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01 -PropertyObject $p

The sixth command displays the Properties property of the resource in the $r2 variable. You can see that the properties have the new values.
PS C:\>$r2.PropertiesName                           Value----                           -----storageRecoveryDefaultState    RunningavailabilityState              0trafficManagerHostNamesrepositorySiteName             ContosoLabWeb2runtimeAvailabilityState       0siteMode                       BasicruntimeADUserlastModifiedTimeUtc            3/25/2014 6:00:04 PMusageState                     0hostNames                      {contosolabweb2.antares-int.windows-int.net}adminEnabled                   TruehostNameSslStates              {System.Collections.Generic.Dictionary`2[System.String,System.Object], System.Collect...runtimeADUserDomainenabled                        TruedeploymentId                   ContosoLabWeb2selfLink                       https://antpreview2.api.admin-antares-int.windows-int.net:454/20130801/websystems/web...computeMode                    DedicatedwebSpace                       ContosoLabsRG-NorthEuropewebspacecsrs                           {}siteConfigintegratedSqlAuthEnabled       Falsestate                          RunningruntimeADUserPasswordserverFarm                     Default2sslCertificates                {}cerscontentAvailabilityState       0enabledHostNames               {contosolabweb2.antares-int.windows-int.net, contosolabweb2.scm.antares-int.windows-i...windowsAuthEnabled             0ownersiteProperties                 {[metadata, ], [properties, System.Collections.Generic.List`1[System.Object]], [appSe...sku                            Basicname                           ContosoLabWeb2
```

This example shows how to change the properties of an Azure resource.
In this case, we'll shift a web site from one server farm to another.
To do that, we have to change the web site properties to be compatible with the new server farm.

### --------------------------  Example 2: Apply a tag to a resource  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource -Name ContosoLabWeb2 -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01 -Tag @{Name="CostCenter";Value="Sales"}
```

This command uses the Tag parameter to add a CostCenter tag with a value of "Sales" to a resource that did not have any existing tags.

### --------------------------  Example 3: Add tags to a resource  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>$tags = (Get-AzureRmResource -Name ContosoWeb -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01).Tags

PS C:\>$tags


Tags: 

      Name        Value
      ====        ======
      Department  IT


PS C:\>$tags += @{Name="Status";Value="Approved"}, @{Name="FY2016"}

PS C:\>Set-AzureRmResource -Name ContosoWeb -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01 -Tag $tags

PS C:>(Get-AzureRmResource -Name ContosoWeb -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01).Tags


Tags: 

      Name        Value
      ====        ======
      Department  IT
      Status      Approved
      FY2016
```

This command adds a "Status" tag with a value of "Approved" and an "FY2016" tag to a resource that has existing tags.
Because the tags you specify replace the existing tags, you must include the existing tags in the new tag collection or you will lose them.

The first command gets all existing tags of the ContosoWeb resource.
It uses the Get-AzureRmResource cmdlet to get the resource and then uses the dot method to get the value of its Tags property.
It saves the existing tags in a $tags variable.The second command gets the tags in the $tags variable.The third command uses a "+=" operator to add the Status and FY2016 tags to the collection (array) of tags in the $tags variable.The fourth command uses the Tag parameter of Set-AzureRmResource to apply the tags in the $tags variable to the ContosoWeb resource.The fifth command shows the effect of the change.
It gets all of the tags applied to the ContosoWeb resource.
The output shows that the resource has the Department tag and the two new tags, Status and FY2015.

### --------------------------  Example 4: Delete all tags  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResource -Name ContosoLabWeb2 -ResourceGroupName ContosoLabsRG -ResourceType "Microsoft.Web/sites" -ApiVersion 2004-04-01 -Tag @{}
```

This command uses the Tag parameter and an empty hash table value to delete all tags from a resource.

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
Do not ask for confirmation.

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
Accept pipeline input: True (ByPropertyName)
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

### -Plan
A hash table which represents resource plan properties.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: PlanObject

Required: False
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

### -Properties
A hash table which represents resource properties.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: PropertyObject

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group of the resource.
Wildcards are not permitted.
This value identifies the resource.
You cannot use this cmdlet to change the resource group of a resource.

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
Specifies the resource type.
Wildcards are not permitted.
This value identifies the resource.
You cannot use this cmdlet to change the resource type.

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

### -Sku
A hash table which represents sku properties.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: SkuObject

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Replaces the tags for the resource with the specified new or predefined tags.
To change any resource tag, you must replace the collection of tags for the resource.A "tag" is a name-value pair that you can apply to resources and resource groups.
Use tags to categorize your resources, such as by department or cost center, or to track notes or comments about the resources.
After you assign tags to resources, you can use the Tag parameters of Get-AzureRmResource and Get-AzureRmResourceGroup to search for resources and groups by tag name or name and value.Each tag must have a Name key.
It can also have an optional Value key with one value.
To specify a new tag, use a hash table, such as @{Name="FY2015"} or @{Name="Department";Value="IT"}.
To specify multiple tags, use commas to separate the hash tables, such as  -Tag @{Name="FY2015"}, @{Name="Department";Value="IT"}.
To specify a predefined tag, use the Get-AzureRmTag cmdlet.To delete a tag, enter a hash table with all tags currently applied to the resource (from Get-AzureRmResource), except for the tag you want to delete. 
To delete all tags from the resource, enter an empty hash table (-Tag @{}).

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

### -UsePatchSemantics
When set indicates if an HTTP PATCH should be used to update the object instead of PUT.

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

### Microsoft.Azure.Commands.ResourceManager.Models.PSResource

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

