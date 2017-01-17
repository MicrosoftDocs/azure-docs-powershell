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
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmApiManagementRegion** cmdlet creates an instance of **PsApiManagementRegion**.
This command is to be used with [New-AzureRmApiManagement](./New-AzureRmApiManagement.md) command.

## EXAMPLES

### Example 1: Create an ApiManagement service
```
$ApimRegion = New-AzureRmApiManagementRegion -Location "Central US" 

$AdditionalRegions = @($ApimRegion)

New-AzureRmApiManagement -ResourceGroupName "ContosoGroup" -Location "West US" -Name "ContosoApi" -Organization "Contoso" -AdminEmail "admin@contoso.com" -AdditionalRegions $AdditionalRegions -Sku "Premium"
```

This example creates an ApiManagement service in West US Region, with an Additional Region in Central US that has a Premium Sku and an organization named Contoso.

### Example 2: Create an ApiManagement service with an external VpnType
```
$ApimRegionVirtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location "Central US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc7-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/centralusvirtualNetwork/subnets/backendSubnet"

$ApimRegion = New-AzureRmApiManagementRegion -Location "Central US" -VirtualNetwork $ApimRegionVirtualNetwork 

$AdditionalRegions = @($apimRegion)

$VirtualNetwork = New-AzureRmApiManagementVirtualNetwork -Location "West US" -SubnetResourceId "/subscriptions/a8ff56dc-3bc2-4174-a1e8-3726ab15d0e2/resourceGroups/ContosoGroup/providers/Microsoft.Network/virtualNetworks/westUsVirtualNetwork/subnets/backendSubnet"

New-AzureRmApiManagement -ResourceGroupName "ContosoGroup" -Location "West US" -Name ContosoApi -Organization "Contoso" -AdminEmail "admin@contoso.com" -AdditionalRegions $AdditionalRegions -VirtualNetwork $VirtualNetwork -VpnType "External" -Sku "Premium"
```

This example creates an ApiManagement service of External VpnType in West US Region, with an Additional Region in Central US.

## PARAMETERS

### -Capacity
Specifies the Sku capacity of the Azure API Management service additional region.
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

### -Location
Specifies the location of the additional deployment region.

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

### -VirtualNetwork
Specifies the Virtual Network Configuration of Azure API Management deployment region.
The default value is $Null.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureRmApiManagementRegion](./Add-AzureRmApiManagementRegion.md)

[Remove-AzureRmApiManagementRegion](./Remove-AzureRmApiManagementRegion.md)
