---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-AzureRmApiManagementRegion

## SYNOPSIS
Removes a deployment region from a **PsApiManagement** object.

## SYNTAX

```
Remove-AzureRmApiManagementRegion -ApiManagement <PsApiManagement> -Location <String> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmApiManagementRegion** cmdlet removes an instance of type **PsApiManagementRegion** from the collection of **AdditionalRegions** objects in a **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement** object.

This cmdlet does not modify deployment by itself, but updates the **PsApiManagement** object in memory.
To update a deployment of the API Management, pass the modified **PsApiManagement** object to the **Update-AzureRmApiManagementDeployment** cmdlet.

## EXAMPLES

### Example 1: Remove a region from a PsApiManagement instance
```
PS C:\> Remove-AzureRmApiManagementRegion -ApiManagement $ApiManagement -Location "East US"
```

This command removes the region named "East US" from the **PsApiManagement** instance.

### Example 2: Remove a region from a PsApiManagement instance and update the deployment
```
PS C:\> Get-AzureRmApiManagement -ResourceGroupName "Contoso" -Name "ContosoApi" | Remove-AzureRmApiManagementRegion -Location "East US" | Update-AzureRmApiManagementDeployment
```

The **Get-AzureRmApiManagement** cmdlet gets an instance of **PsApiManagement** representing the API Management service named "ContosoApi" in the resource group named "Contoso".
The **PsApiManagement** object is passed to the **Remove-AzureRmApiManagementRegion** cmdlet, which removes the region named "East US" from the object.
The modified **PsApiManagement** object is then passed to the **Update-AzureRmApiManagementDeployment** cmdlet, which updates the deployment.

## PARAMETERS

### -ApiManagement
Specifies the **PsApiManagement** object from which to remove the deployment region.

```yaml
Type: PsApiManagement
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the location of the deployment region to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: North Central US, South Central US, Central US, West Europe, North Europe, West US, East US, East US 2, Japan East, Japan West, Brazil South, Southeast Asia, East Asia, Australia East, Australia Southeast

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement
### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Add-AzureRmApiManagementRegion](./Add-AzureRmApiManagementRegion.md)

[Update-AzureRmApiManagementDeployment](./Update-AzureRmApiManagementDeployment.md)
