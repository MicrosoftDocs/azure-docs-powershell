---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
online version: .\Remove-AzureApiManagementRegion.md
schema: 2.0.0
---

# Add-AzureApiManagementRegion

## SYNOPSIS
Adds a deployment region to the PsApiManagement instance.

## SYNTAX

```
Add-AzureApiManagementRegion -ApiManagement <PsApiManagement> -Location <String> [-Sku <PsApiManagementSku>]
 [-Capacity <Int32>] [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureApiManagementRegion** cmdlet adds an instance of type **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementRegion** to a collection of **AdditionalRegions** of provided instance of type **Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement**.
This cmdlet does not deploy anything by itself but updates the instance of **PsApiManagement** in-memory.
To update the deployment of API Management, pass the modified **PsApiManagementInstance** to the Update-AzureApiManagementDeployment cmdlet.

## EXAMPLES

### Example 1: Add new deployment regions to a PsApiManagement instance
```
PS C:\>Add-AzureApiManagementRegion -ApiManagement $ApiManagement -Location "East US" -Sku "Premium" -Capacity 2
```

This command adds two premium SKU units and the region named East US to the **PsApiManagement** instance.

### Example 2: Add new deployment regions to a PsApiManagement instance and then update deployment
```
PS C:\>Get-AzureApiManagement -ResourceGroupName "Contoso" -Name "ContosoApi" | Add-AzureApiManagementRegion -Location "East US" -Sku "Premium" -Capacity 2
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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the location of the new deployment region.

Valid values are: 

- North Central US
- South Central US
- Central US
- West Europe
- North Europe
- West US
- East US
- East US 2
- Japan East
- Japan West
- Brazil South
- Southeast Asia
- East Asia
- Australia East
- Australia Southeast

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

- Developer
- Standard
- Premium

```yaml
Type: PsApiManagementSku
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Capacity
Specifies the SKU capacity of the deployment region.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
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

## OUTPUTS

## NOTES
* The cmdlet writes updated **PsApiManagement** instance to pipeline.

## RELATED LINKS

[Remove-AzureApiManagementRegion](.\Remove-AzureApiManagementRegion.md)

[Update-AzureApiManagementRegion](.\Update-AzureApiManagementRegion.md)

[Update-AzureApiManagementDeployment](.\Update-AzureApiManagementDeployment.md)

