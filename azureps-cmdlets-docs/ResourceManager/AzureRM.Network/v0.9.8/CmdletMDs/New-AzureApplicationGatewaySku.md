---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureApplicationGatewaySku.md
schema: 2.0.0
---

# New-AzureApplicationGatewaySku

## SYNOPSIS
Creates a SKU for an application gateway.

## SYNTAX

```
New-AzureApplicationGatewaySku -Name <String> -Tier <String> -Capacity <Int32> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGatewaySku** cmdlet creates a stock keeping unit (SKU) for an Azure application gateway.

## EXAMPLES

### Example 1: Create a SKU for an azure_2 application gateway
```
PS C:\>$SKU = New-AzureApplicationGatewaySku -Name "Standard_Small" -Tier "Standard" -Capacity 2
```

This command creates a SKU named Standard_Small for an Azure application gateway.

## PARAMETERS

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

### -Name
Specifies the name of the SKU.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Standard_Small, Standard_Medium, Standard_Large

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySku

## NOTES

## RELATED LINKS

[Get-AzureApplicationGatewaySku](.\Get-AzureApplicationGatewaySku.md)

[Set-AzureApplicationGatewaySku](.\Set-AzureApplicationGatewaySku.md)

