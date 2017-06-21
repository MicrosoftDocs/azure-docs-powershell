---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Add-AzureRmApiManagementRegion

## SYNOPSIS
Adds a new deployment region to a **PsApiManagement** object.

## SYNTAX

```
Add-AzureRmApiManagementRegion -ApiManagement <PsApiManagement> -Location <String> [-Sku <PsApiManagementSku>]
 [-Capacity <Int32>] [-VirtualNetwork <PsApiManagementVirtualNetwork>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureRmApiManagementRegion** cmdlet adds a new instance of type **PsApiManagementRegion** to the collection of **AdditionalRegions** objects in a **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement** object.

This cmdlet does not deploy anything by itself, but updates the **PsApiManagement** object in memory.
To update a deployment of the API Management, pass the modified **PsApiManagement** object to the **Update-AzureRmApiManagementDeployment** cmdlet.

## EXAMPLES

### Example 1: Add a new deployment region to a PsApiManagement instance
```
PS C:\> Add-AzureRmApiManagementRegion -ApiManagement $ApiManagement -Location "East US" -Sku "Premium" -Capacity 2
```

This command adds the region named "East US" with two premium SKU units to the **PsApiManagement** instance.

### Example 2: Add a new deployment region to a PsApiManagement instance and update the deployment
```
PS C:\> Get-AzureRmApiManagement -ResourceGroupName "Contoso" -Name "ContosoApi" | Add-AzureRmApiManagementRegion -Location "East US" -Sku "Premium" -Capacity 2 | Update-AzureRmApiManagementDeployments
```

This command gets a **PsApiManagement** object, adds the region named "East US" with two premium SKU units, and then updates the deployment.

## PARAMETERS

### -ApiManagement
Specifies the **PsApiManagement** object to which the deployment region is being added.

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

### -Capacity
Specifies the SKU capacity of the deployment region.
The default value is 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location of the new deployment region.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: North Central US, South Central US, Central US, West Europe, North Europe, West US, East US, East US 2, Japan East, Japan West, Brazil South, Southeast Asia, East Asia, Australia East, Australia Southeast

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Specifies the tier of the deployment region. Valid values are Developer, Standard, and Premium.
The default value is Developer.

```yaml
Type: PsApiManagementSku
Parameter Sets: (All)
Aliases:
Accepted values: Developer, Standard, Premium

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies the virtual network configuration.
The default value is $null.

```yaml
Type: PsApiManagementVirtualNetwork
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

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Remove-AzureRmApiManagementRegion](./Remove-AzureRmApiManagementRegion.md)

[Update-AzureRmApiManagementDeployment](./Update-AzureRmApiManagementDeployment.md)

[Update-AzureRmApiManagementRegion](./Update-AzureRmApiManagementRegion.md)
