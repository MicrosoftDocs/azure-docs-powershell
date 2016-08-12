---
external help file: RMAzure_Apimanagement.xml
online version: a6e4fc8a-f5c6-4f8e-8ed9-5ee80150b119
schema: 2.0.0
---

# Update-AzureRmApiManagementRegion
## SYNOPSIS
Updates existing deployment region in PsApiManagement instance.

## SYNTAX

```
Update-AzureRmApiManagementRegion [-VirtualNetwork <PsApiManagementVirtualNetwork>]
 -ApiManagement <PsApiManagement> -Capacity <Int32> -Location <String> [-Sku]
```

## DESCRIPTION
The **Update-AzureRmApiManagementRegion** cmdlet updates an existing instance of type **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** in a collection of **AdditionalRegions** objects of a provided instance of type **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
This cmdlet does not deploy anything but updates an instance of **PsApiManagement** in-memory.
To update a deployment of an API Management use the modified **PsApiManagementInstance** to the Update-AzureRmApiManagementDeployment cmdlet.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ApiManagement
Specifies the **PsApiManagement** instance to update an existing deployment region in.

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
Specifies the new SKU capacity value for the deployment region.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location of the deployment region to update.

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
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Specifies the new tier value for the deployment region.

Valid values are: 

-- Developer
-- Standard
-- Premium

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Developer, Standard, Premium

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies a virtual network configuration for the deployment region.
Passing $null will remove virtual network configuration for the region.

```yaml
Type: PsApiManagementVirtualNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRmApiManagementRegion](a6e4fc8a-f5c6-4f8e-8ed9-5ee80150b119)

[Remove-AzureRmApiManagementRegion](6df0b014-03b0-47aa-9d34-9d0fceee2247)

[Update-AzureRmApiManagementDeployment](166e3bd3-929d-4213-aebc-411e2e8f50a2)

