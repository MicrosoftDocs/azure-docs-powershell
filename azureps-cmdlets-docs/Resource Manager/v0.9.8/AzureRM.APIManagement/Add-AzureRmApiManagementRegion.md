---
external help file: RMAzure_Apimanagement.xml
online version: 6df0b014-03b0-47aa-9d34-9d0fceee2247
schema: 2.0.0
---

# Add-AzureRmApiManagementRegion
## SYNOPSIS
Adds new deployment regions to a PsApiManagement instance.

## SYNTAX

```
Add-AzureRmApiManagementRegion [-Capacity <Int32]>] [-Sku <PsApiManagementSku]>]
 [-VirtualNetwork <PsApiManagementVirtualNetwork>] -ApiManagement <PsApiManagement> -Location <String>
```

## DESCRIPTION
The **Add-AzureRmApiManagementRegion** cmdlet adds new instance of type **PsApiManagementRegion** to the collection of **AdditionalRegions** of provided instance of type **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
This cmdlet does not deploy anything by itself but updates instance of **PsApiManagement** in-memory.
To update a deployment of an API Management pass the modified **PsApiManagement** Instance to Update-AzureRmApiManagementDeployment.

## EXAMPLES

### Example 1: Add new deployment regions to a PsApiManagement instance
```
PS C:\>Add-AzureRmApiManagementRegion -ApiManagement $ApiManagement -Location "East US" -Sku "Premium" -Capacity 2
```

This command adds two premium SKU units and the region named East US to the **PsApiManagement** instance.

### Example 2: Add new deployment regions to a PsApiManagement instance and then update deployment
```
PS C:\>Get-AzureRmApiManagement -ResourceGroupName "Contoso" -Name "ContosoApi" | Add-AzureRmApiManagementRegion -Location "East US" -Sku "Premium" -Capacity 2 | Update-AzureRmApiManagementDeployments
```

This command gets a **PsApiManagement** object, adds two premium SKU units for the region named East US, and then updates deployment.

## PARAMETERS

### -ApiManagement
Specifies the **PsApiManagement** instance that this cmdlet adds additional deployment regions to.

```yaml
Type: PsApiManagement
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Capacity
Specifies the SKU capacity of the deployment region.

```yaml
Type: Int32]
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

Valid values are: 

-- North Central US
-- South Central US
-- Central US
-- West Europe
-- North Europe
-- West US
-- East US
-- East US 2
-- Japan East
-- Japan West
-- Brazil South
-- Southeast Asia
-- East Asia
-- Australia East
-- Australia Southeast

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Specifies the tier of the deployment region.
Valid values are: 

-- Developer
-- Standard
-- Premium

```yaml
Type: PsApiManagementSku]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies a virtual network configuration.

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

## INPUTS

## OUTPUTS

## NOTES
The cmdlet writes updated **PsApiManagement** instance to pipeline.

## RELATED LINKS

[Remove-AzureRmApiManagementRegion](6df0b014-03b0-47aa-9d34-9d0fceee2247)

[Update-AzureRmApiManagementRegion](bf37a79f-38a4-433e-b847-beb564ad781c)

[Update-AzureRmApiManagementDeployment](166e3bd3-929d-4213-aebc-411e2e8f50a2)

