---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
online version: be20f75a-85e2-48b3-b35f-ad8ce3788a82
schema: 2.0.0
---

# Get-AzureVNetConnection

## SYNOPSIS
Gets connections to an Azure virtual network.

## SYNTAX

```
Get-AzureVNetConnection [-VNetName] <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureVNetConnection** cmdlet returns an object that specifies all active virtual private network (VPN) connections to an Azure virtual network.
VPN connections include cross premises site-to-site VPNs and virtual network to virtual network connections.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -VNetName
Specifies the name of the virtual network from which this cmdlet returns connections.

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

