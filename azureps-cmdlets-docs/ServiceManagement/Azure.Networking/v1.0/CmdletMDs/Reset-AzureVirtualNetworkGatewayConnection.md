---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVirtualNetworkGatewayConnection.md
schema: 2.0.0
---

# Reset-AzureVirtualNetworkGatewayConnection

## SYNOPSIS
Resets a virtual network gateway connection.

## SYNTAX

```
Reset-AzureVirtualNetworkGatewayConnection [-GatewayId] <String> [-ConnectedEntityId] <String>
 [-RoutingWeight] <Int32> [[-SharedKey] <String>] [[-EnableBgp] <Boolean>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Reset-AzureVirtualNetworkGatewayConnection** cmdlet resets a virtual network gateway connection.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ConnectedEntityId
Specifies the ID of a connected entity.

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

### -EnableBgp
Enables Border Gateway Protocol (BGP).

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayId
Specifies the ID of a gateway.

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

### -Profile
ps_azureprofile_description

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

### -RoutingWeight
```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedKey
Specifies a shared key.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVirtualNetworkGatewayConnection](.\Get-AzureVirtualNetworkGatewayConnection.md)

[New-AzureVirtualNetworkGatewayConnection](.\New-AzureVirtualNetworkGatewayConnection.md)

[Remove-AzureVirtualNetworkGatewayConnection](.\Remove-AzureVirtualNetworkGatewayConnection.md)

