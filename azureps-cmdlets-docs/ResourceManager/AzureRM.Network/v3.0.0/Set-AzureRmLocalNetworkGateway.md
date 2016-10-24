---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 71a058cd-cb69-4877-8ec7-52fefb23fdc4
schema: 2.0.0
ms.assetid: 565FDFFF-B140-4F6A-BD0B-BFA9B63DEF09
---

# Set-AzureRmLocalNetworkGateway

## SYNOPSIS
Modifies a local network gateway.

## SYNTAX

```
Set-AzureRmLocalNetworkGateway -LocalNetworkGateway <PSLocalNetworkGateway>
 [-AddressPrefix <System.Collections.Generic.List`1[System.String]>] [-Asn <UInt32>]
 [-BgpPeeringAddress <String>] [-PeerWeight <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmLocalNetworkGateway** cmdlet modifies a local network gateway.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -LocalNetworkGateway
```yaml
Type: PSLocalNetworkGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AddressPrefix
```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Asn
```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BgpPeeringAddress
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

### -PeerWeight
```yaml
Type: Int32
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

[Get-AzureRmLocalNetworkGateway](.\Get-AzureRmLocalNetworkGateway.md)

[New-AzureRmLocalNetworkGateway](.\New-AzureRmLocalNetworkGateway.md)

[Remove-AzureRmLocalNetworkGateway](.\Remove-AzureRmLocalNetworkGateway.md)


