---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Get-AzureVNetGatewayKey.md
schema: 2.0.0
---

# Set-AzureVNetGatewayKey

## SYNOPSIS
Sets the pre-shared key for the connection between an Azure VPN gateway and a local network site.

## SYNTAX

```
Set-AzureVNetGatewayKey [-VNetName] <String> [-LocalNetworkSiteName] <String> [-SharedKey] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVNetGatewayKey** cmdlet sets the pre-shared key for the connection between an Azure virtual private network (VPN) gateway and an on-premises local network site.
The key must be equal to the key configured on the gateway of the local network site.
If the keys do not match, a connection cannot establish.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -VNetName
Specifies the virtual network for which this cmdlet sets the shared key for the connection.

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

### -LocalNetworkSiteName
Specifies the name of the local network site that connects to the virtual network gateway.

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

### -SharedKey
Specifies the shared key to assign to the VPN gateway.
The value must be an alpha-numerical string no longer than 128 characters.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVNetGatewayKey](.\Get-AzureVNetGatewayKey.md)

