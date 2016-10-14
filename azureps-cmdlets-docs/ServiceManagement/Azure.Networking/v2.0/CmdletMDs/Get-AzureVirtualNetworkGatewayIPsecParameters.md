---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Set-AzureVirtualNetworkGatewayIPsecParameters.md
schema: 2.0.0
---

# Get-AzureVirtualNetworkGatewayIPsecParameters

## SYNOPSIS
Gets the IPsec parameters for an Azure virtual network gateway.

## SYNTAX

```
Get-AzureVirtualNetworkGatewayIPsecParameters [-GatewayId] <String> [-ConnectedEntityId] <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVirtualNetworkGatewayIPsecParameters** cmdlet gets the IPsec parameters for an Azure virtual network gateway.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ConnectedEntityId
Specifies the ID of a connected entitiy.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureVirtualNetworkGatewayIPsecParameters](.\Set-AzureVirtualNetworkGatewayIPsecParameters.md)

