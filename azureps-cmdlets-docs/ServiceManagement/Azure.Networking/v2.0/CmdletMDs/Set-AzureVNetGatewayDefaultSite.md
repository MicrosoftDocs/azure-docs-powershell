---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: .\Remove-AzureVNetGatewayDefaultSite.md
schema: 2.0.0
---

# Set-AzureVNetGatewayDefaultSite

## SYNOPSIS
Sets the default site for forced tunneling traffic.

## SYNTAX

```
Set-AzureVNetGatewayDefaultSite [-VNetName] <String> [-DefaultSite] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVNetGatewayDefaultSite** cmdlet sets the default route to the on-premises site for forced tunneling traffic.
This command sets the route on an Azure virtual private network (VPN) gateway for a virtual network.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -VNetName
Specifies a virtual network.
This cmdlet sets the default route of the VPN gateway for forced tunneling traffic for the virtual network that this parameter specifies.

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

### -DefaultSite
Specifies the name of the on-premises local network site for forced tunneling traffic.

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

[Remove-AzureVNetGatewayDefaultSite](.\Remove-AzureVNetGatewayDefaultSite.md)

