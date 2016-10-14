---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureVirtualNetworkSubnetConfig.md
schema: 2.0.0
---

# Remove-AzureVirtualNetworkSubnetConfig

## SYNOPSIS
Removes a subnet configuration from a virtual network.

## SYNTAX

```
Remove-AzureVirtualNetworkSubnetConfig [-Name <String>] -VirtualNetwork <PSVirtualNetwork>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureVirtualNetworkSubnetConfig** cmdlet removes a subnet from an Azure virtual network.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of the subnet configuration to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

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

### -VirtualNetwork
Specifies the **VirtualNetwork** object that contains the subnet configuration to remove.

```yaml
Type: PSVirtualNetwork
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureVirtualNetworkSubnetConfig](.\Add-AzureVirtualNetworkSubnetConfig.md)

[Get-AzureVirtualNetworkSubnetConfig](.\Get-AzureVirtualNetworkSubnetConfig.md)

[New-AzureVirtualNetworkSubnetConfig](.\New-AzureVirtualNetworkSubnetConfig.md)

[Set-AzureVirtualNetworkSubnetConfig](.\Set-AzureVirtualNetworkSubnetConfig.md)

