---
external help file: Microsoft.Azure.Commands.ApiManagement.dll-Help.xml
ms.assetid: A4226BFB-AB3B-4883-9D52-5EB7F29D8A71
online version: 
schema: 2.0.0
---

# New-AzureRmApiManagementRegion

## SYNOPSIS
Creates an instance of PsApiManagementRegion.

## SYNTAX

```
New-AzureRmApiManagementRegion -Location <String> [-Capacity <Int32>]
 [-VirtualNetwork <PsApiManagementVirtualNetwork>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

## DESCRIPTION
Helper command to create an instance of **PsApiManagementRegion**.
This command is to be used with [New-AzureRmApiManagement](./New-AzureRmApiManagement.md) command.

## EXAMPLES

### Example 1: Create an instance of PsApiManagementRegion

```
$ApiMRegion = New-AzureRmApiManagementRegion -Location "Central US" 

$AdditionalRegions = @($ApiMRegion)

New-AzureRmApiManagement -ResourceGroupName "Contoso"Group -Location "West US" -Name "ContosoApi" -Organization "Contoso" -AdminEmail "admin@contoso.com" -AdditionalRegions $AdditionalRegions -Sku "Premium"
```

### Example 2: an instance of PsApiManagementRegion with an additional region

```
$ApiMRegionVirtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location "Central US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/centralusvirtualNetwork/subnets/backendSubnet"

$ApiMRegion = New-AzureRmApiManagementRegion -Location "Central US" -VirtualNetwork $ApiMRegionVirtualNetwork 

$AdditionalRegions = @($ApiMRegion)

$virtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location "West US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc2-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/westUsVirtualNetwork/subnets/backendSubnet"

New-AzureRmApiManagement -ResourceGroupName "Contoso"Group -Location "West US" -Name "ContosoApi" -Organization "Contoso" -AdminEmail "admin@contoso.com" -AdditionalRegions $AdditionalRegions -VirtualNetwork $virtualNetwork -VpnType "External" -Sku "Premium"
```

This example creates an ApiManagement service of External VpnType in West US Region, with an Additional Region in Central US.

## PARAMETERS

### -Location
Specifies the geographical location of the additional deployment region.

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

### -Capacity
Specifies the SKU capacity of the Azure API Management service additional region.
Default value is 1.

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
Specifies the Virtual Network Configuration of Azure API Management deployment region.
Default value is $Null.

```yaml
Type: PsApiManagementVirtualNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRmApiManagementRegion](./Add-AzureRmApiManagementRegion.md)

[Remove-AzureRmApiManagementRegion](./Remove-AzureRmApiManagementRegion.md)

[Update-AzureRmApiManagementRegion](./Update-AzureRmApiManagementRegion.md)
