---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayBackendAddressPool.md
schema: 2.0.0
---

# New-AzureApplicationGatewayBackendAddressPool

## SYNOPSIS
Creates a back-end address pool for an application gateway.

## SYNTAX

### SetByResourceId
```
New-AzureApplicationGatewayBackendAddressPool -Name <String>
 [-BackendIPConfigurationIds <System.Collections.Generic.List`1[System.String]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SetByIP
```
New-AzureApplicationGatewayBackendAddressPool -Name <String>
 [-BackendIPAddresses <System.Collections.Generic.List`1[System.String]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SetByFqdn
```
New-AzureApplicationGatewayBackendAddressPool -Name <String>
 [-BackendFqdns <System.Collections.Generic.List`1[System.String]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGatewayBackendAddressPool** cmdlet creates a back-end address pool for an Azure application gateway.
A back-end address can be specified as an IP address, a fully-qualified domain name (FQDN) or an IP configuration ID.

## EXAMPLES

### Example 1: Create a back-end address pool by using the FQDN of a back-end server
```
PS C:\>$Pool = New-AzureApplicationGatewayBackendAddressPool -Name "Pool01" -BackendFqdns "contoso1.com", "contoso2.com"
```

This command creates a back-end address pool named Pool01 by using the FQDNs of back-end servers, and stores it in the $Pool variable.

### Example 2: Create a back-end address pool by using the IP address of a back-end server
```
PS C:\>$Pool = New-AzureApplicationGatewayBackendAddressPool -Name "Pool02" -BackendFqdns "10.10.10.10", "10.10.10.11"
```

This command creates a back-end address pool named Pool02 by using the IP addresses of back-end servers, and stores it in the $Pool variable.

## PARAMETERS

### -BackendFqdns
Specifies a list of back-end FQDNs that this cmdlet associates with the back-end server pool.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByFqdn
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendIPAddresses
Specifies a list of back-end IP addresses that this cmdlet associates with the back-end server pool.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendIPConfigurationIds
Specifies a list of back-end server IP configuration IDs that this cmdlet associates with the back-end server pool.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the back-end server pool that this cmdlet creates.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayBackendAddressPool](.\Add-AzureApplicationGatewayBackendAddressPool.md)

[Get-AzureApplicationGatewayBackendAddressPool](.\Get-AzureApplicationGatewayBackendAddressPool.md)

[Remove-AzureApplicationGatewayBackendAddressPool](.\Remove-AzureApplicationGatewayBackendAddressPool.md)

[Set-AzureApplicationGatewayBackendAddressPool](.\Set-AzureApplicationGatewayBackendAddressPool.md)

