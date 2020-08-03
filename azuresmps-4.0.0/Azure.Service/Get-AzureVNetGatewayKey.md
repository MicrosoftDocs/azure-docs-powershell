---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 8AD101BA-9275-4B2B-BB31-99FC34B8D1E8
online version: 
schema: 2.0.0
---

# Get-AzureVNetGatewayKey

## SYNOPSIS
Gets the pre-shared key for the connection between a virtual network gateway and a local network site.

## SYNTAX

```
Get-AzureVNetGatewayKey -VNetName <String> -LocalNetworkSiteName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVNetGatewayKey** cmdlet gets the pre-shared key for the connection between a virtual network gateway and a local network site.

## EXAMPLES

## PARAMETERS

### -LocalNetworkSiteName
Specifies the name of the local network site that connects to the virtual network gateway.

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
Specifies the virtual network for which this cmdlet gets the shared key for connections.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureVNetGatewayKey](./Set-AzureVNetGatewayKey.md)


