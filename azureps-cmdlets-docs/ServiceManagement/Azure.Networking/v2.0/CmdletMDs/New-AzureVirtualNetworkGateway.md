---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVirtualNetworkGateway.md
schema: 2.0.0
---

# New-AzureVirtualNetworkGateway

## SYNOPSIS
Creates an Azure virtual network gateway.

## SYNTAX

```
New-AzureVirtualNetworkGateway [-VNetName] <String> [-GatewayName] <String> [[-GatewayType] <String>]
 [[-GatewaySKU] <String>] [[-Location] <String>] [[-VnetId] <String>] [[-Asn] <UInt32>] [[-PeerWeight] <Int32>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVirtualNetworkGateway** cmdlet creates an Azure virtual network gateway.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Asn
Specifies the autonomous system number (ASN).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayName
Specifies the name of the gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewaySKU
Specifies the SKU of the virtual network gateway that this cmdlet creates.
Valid values are: 

- Default 
- Standard 
- HighPerformance

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayType
Specifies the type of gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeerWeight
```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetName
Specifies a virtual network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VnetId
Specifies the ID of a virtual network.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVirtualNetworkGateway](.\Get-AzureVirtualNetworkGateway.md)

[Remove-AzureVirtualNetworkGateway](.\Remove-AzureVirtualNetworkGateway.md)

[Resize-AzureVirtualNetworkGateway](.\Resize-AzureVirtualNetworkGateway.md)

