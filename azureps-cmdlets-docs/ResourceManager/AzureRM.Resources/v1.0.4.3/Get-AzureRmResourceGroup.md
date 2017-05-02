---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393047
schema: 2.0.0
---

# Get-AzureRmResourceGroup

## SYNOPSIS
Gets Azure resource groups

## SYNTAX

### Lists the resource group based in the name. (Default)
```
Get-AzureRmResourceGroup [-Name <String>] [-Location <String>] [<CommonParameters>]
```

### Lists the resource group based in the Id.
```
Get-AzureRmResourceGroup [-Location <String>] [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmResourceGroup cmdlet gets the Azure resource groups in your subscription.
You can use the Name parameter to select resource groups by name.
The default is all resource groups.An Azure resource is a user-managed Azure entity, such as a database server, database, or web site.
An Azure resource group is a collection of Azure resources that are deployed as a unit.

## EXAMPLES

### --------------------------  Example 1: Get all resource groups and their details  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup -Detailed
Name:      Contoso
Location:  West US
Resources: 
           Name             Type                     Location
           ===============  =======================  ========
           ConstosoWebSite  Microsoft.Web/sites      West US
           sqlsvr03         Microsoft.Sql/servers    West US
           sqldb01          Microsoft.Sql/databases  West US

Name:      EngineerBlog
Location:  East US
Resources: 
           Name             Type                     Location
           ===============  =======================  ========
           EngineerBlog     Microsoft.Web/sites      West US
           EngSvr01         Microsoft.Sql/servers    West US
           EngDB02          Microsoft.Sql/databases  West US
```

This command gets all resource groups in the subscription.

### --------------------------  Example 2: Get resource groups by name  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup -Name EngineerBlog
Name:      EngineerBlog
Location:  East US
Resources: 
           Name             Type                     Location
           ===============  =======================  ========
           EngineerBlog     Microsoft.Web/sites      West US
           EngSvr01         Microsoft.Sql/servers    West US
           EngDB02          Microsoft.Sql/databases  West US
```

This command gets Azure resource groups in your subscription that have names that begin with "eng".

### --------------------------  Example 3: Get resource groups by other properties  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup -Detailed | Where-Object {$_.Resources.Type -like "*serverFarms*"} | Select-Object -Property ResourceGroupName
Contoso
EngineerBlog
```

The command uses the Where-Object, ForEach-Object, and Select-Object cmdlets to get the names of resource groups that include Azure database server farms.
You can use commands like this one to find resource groups with resources or properties of interest.

The command uses the Get-AzureRmResourceGroup cmdlet to get all resource groups in the subscription.
It pipes the resource groups to the Where-Object cmdlet, which returns only the resource groups that include server farm resources.
The command pipes those resource groups to the Select-Object cmdlet, which returns only the value of the ResourceGroupName property of each resource group.

### --------------------------  Example 4: Get resource groups by tag  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup -Tag @{Name="CostCenter";Value="Development"}

PS C:\>Get-AzureRmResourceGroup -Tag @{Name="CostCenter"}
```

These commands get resource groups by tag.
The first command gets resource groups that have a "CostCenter" tag with a value of "Development".
The second command gets all resource groups that have a "CostCenter" tag, regardless of its value.

### --------------------------  Example 5: Get all tags of a resource group  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup -Name ContosoRG

PS C:\>(Get-AzureRmResourceGroup -Name ContosoRG).Tags

Tags: 

      Name        Value
      ====        ======
      Department  IT
      Status      Approved
      FY2016
```

These commands get all tags of the ContosoRG  resource group. 
The first command gets the resource group by name with all of its properties.
The second command, which uses the Tags property of the output object, gets only the tags.

## PARAMETERS

### -Id
The resource group Id.

```yaml
Type: String
Parameter Sets: Lists the resource group based in the Id.
Aliases: ResourceGroupId, ResourceId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
The resource group location.

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

### -Name
{{Fill Name Description}}

```yaml
Type: String
Parameter Sets: Lists the resource group based in the name.
Aliases: ResourceGroupName

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

### Microsoft.Azure.Commands.ResourceManagement.PSResourceGroup

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[New-AzureRmResourceGroup]()

[Remove-AzureRmResourceGroup]()

