---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmApplicationGatewaySku

## SYNOPSIS
Creates a SKU for an application gateway.

## SYNTAX

```
New-AzureRmApplicationGatewaySku -Name <String> -Tier <String> -Capacity <Int32> [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmApplicationGatewaySku cmdlet creates a stock keeping unit (SKU) for an Azure application gateway.

## EXAMPLES

### --------------------------  Example 1: Create a SKU for an azure_2 application gateway  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$SKU = New-AzureRmApplicationGatewaySku -Name "Standard_Small" -Tier "Standard" -Capacity 2
```

This command creates a SKU named Standard_Small for an Azure application gateway.

## PARAMETERS

### -Name
Specifies the name of the SKU.

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

### -Tier
Specifies the tier of SKU.

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
Specifies the number of instances of an application gateway.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySku

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmApplicationGatewaySku]()

[Set-AzureRmApplicationGatewaySku]()

