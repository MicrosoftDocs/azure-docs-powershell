---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393047
schema: 2.0.0
---

# Get-AzureRmResourceGroup

## SYNOPSIS
Gets Azure resource groups

## SYNTAX

### Lists the resource group based on the name. (Default)
```
Get-AzureRmResourceGroup [-Name <String>] [-Location <String>] [-ApiVersion <String>] [-Pre]
 [<CommonParameters>]
```

### Lists the resource group based on the Id.
```
Get-AzureRmResourceGroup [-Location <String>] [-Id <String>] [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureRmResourceGroup cmdlet gets the Azure resource groups in your subscription.
You can use the Name parameter to select resource groups by name.
The default is all resource groups.
An Azure resource is a user-managed Azure entity, such as a database server, database, or web site.
An Azure resource group is a collection of Azure resources that are deployed as a unit.

If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Example 1: Get all resource groups and their details  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup 
          ResourceGroupName : Api-Default-West-US
          Location          : westus
          ProvisioningState : Succeeded
          Tags              :
          ResourceId        : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/Api-Default-West-US

          ResourceGroupName : AzureResourceGroup3
          Location          : centralus
          ProvisioningState : Succeeded
          Tags              :
          ResourceId        : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/AzureResourceGroup3
```

This command gets all resource groups in the subscription.

### --------------------------  Example 2: Get resource group by name  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup -Name AzureResourceGroup3
          ResourceGroupName : AzureResourceGroup3
          Location          : centralus
          ProvisioningState : Succeeded
          Tags              :
          ResourceId        : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/AzureResourceGroup3
```

This command gets the Azure resource group in your subscription which has the name AzureResourceGroup3.

### --------------------------  Example 3: Get all tags of a resource group  --------------------------
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

### -Id
Specifies the id of the resource group.
Wildcards are not permitted.
This parameter is optional.
The default is all resource groups in the subscription

```yaml
Type: String
Parameter Sets: Lists the resource group based on the Id.
Aliases: ResourceGroupId, ResourceId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location of the resource group.

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
Parameter Sets: Lists the resource group based on the name.
Aliases: ResourceGroupName

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

