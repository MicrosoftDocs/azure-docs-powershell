---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 0E4D44EE-BF28-46FE-B2FA-D35C1651016F
online version: 
schema: 2.0.0
---

# Reset-AzureLocalNetworkGateway

## SYNOPSIS
Resets a local network gateway.

## SYNTAX

```
Reset-AzureLocalNetworkGateway [-GatewayId] <String>
 [-AddressSpace] <System.Collections.Generic.List`1[System.String]> [[-Asn] <UInt32>]
 [[-BgpPeeringAddress] <String>] [[-PeerWeight] <Int32>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-AzureLocalNetworkGateway** cmdlet resets a local network gateway.

## EXAMPLES


## PARAMETERS

### -GatewayId
Specifies the ID of the gateway.

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

### -AddressSpace
Specifies the address space.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Asn
Specifies the autonomous system number (ASN).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BgpPeeringAddress
Specifies the Border Gateway Protocol (BGP) peering address.

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

### -PeerWeight
```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

[Get-AzureLocalNetworkGateway](./Get-AzureLocalNetworkGateway.md)

[New-AzureLocalNetworkGateway](./New-AzureLocalNetworkGateway.md)

[Remove-AzureLocalNetworkGateway](./Remove-AzureLocalNetworkGateway.md)


