---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVirtualNetworkGatewayConnection.md
schema: 2.0.0
---

# New-AzureVirtualNetworkGatewayConnection

## SYNOPSIS
Creates an azure_2 virtual gateway network connection.

## SYNTAX

```
New-AzureVirtualNetworkGatewayConnection [-ConnectedEntityId] <String> [-GatewayConnectionName] <String>
 [-GatewayConnectionType] <String> [[-RoutingWeight] <Int32>] [[-SharedKey] <String>]
 [-VirtualNetworkGatewayId] <String> [[-EnableBgp] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVirtualNetworkGatewayConnection** cmdlet creates an azure_2 virtual gateway network connection.

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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableBgp
Enables Border Gateway Protocol (BGP).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayConnectionName
Specifies a name for the gateway connection.

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

### -GatewayConnectionType
Specifies the type of gateway connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

Required: False
Position: 3
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
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkGatewayId
Specifies the ID of a virtual network gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-AzureVirtualNetworkGatewayConnection](.\Get-AzureVirtualNetworkGatewayConnection.md)

[Remove-AzureVirtualNetworkGatewayConnection](.\Remove-AzureVirtualNetworkGatewayConnection.md)

[Reset-AzureVirtualNetworkGatewayConnection](.\Reset-AzureVirtualNetworkGatewayConnection.md)

