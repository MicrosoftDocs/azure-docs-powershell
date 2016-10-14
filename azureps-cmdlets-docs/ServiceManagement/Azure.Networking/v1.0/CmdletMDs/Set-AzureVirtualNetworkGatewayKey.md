---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVirtualNetworkGatewayKey.md
schema: 2.0.0
---

# Set-AzureVirtualNetworkGatewayKey

## SYNOPSIS
Sets the key for an azure_2 virtual network gateway.

## SYNTAX

```
Set-AzureVirtualNetworkGatewayKey [-GatewayId] <String> [-ConnectedEntityId] <String> [-SharedKey] <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVirtualNetworkGatewayKey** cmdlet sets the key for an azure_2 virtual network gateway.

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

### -GatewayId
Specifies the ID of a gateway

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

### -SharedKey
Specifies a shared key.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVirtualNetworkGatewayKey](.\Get-AzureVirtualNetworkGatewayKey.md)

[Reset-AzureVirtualNetworkGatewayKey](.\Reset-AzureVirtualNetworkGatewayKey.md)

