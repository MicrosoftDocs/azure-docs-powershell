---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayBackendHttpSettings.md
schema: 2.0.0
---

# New-AzureApplicationGatewayBackendHttpSettings

## SYNOPSIS
Creates back-end HTTP settings for an application gateway.

## SYNTAX

```
New-AzureApplicationGatewayBackendHttpSettings -Name <String> -Port <Int32> -Protocol <String>
 -CookieBasedAffinity <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGatewayBackendHttpSettings** cmdlet creates back-end HTTP settings for an application gateway.
Back-end HTTP settings are applied to all back-end servers in a pool.

## EXAMPLES

### Example 1: Create back-end HTTP settings
```
PS C:\> $Setting = New-AzureApplicationGatewayBackendHttpSettings -Name "Setting01" -Port 80 -Protocol Http -CookieBasedAffinity Disabled
```

This command creates back-end HTTP settings named Setting01 on port 80, using the HTTP protocol, with cookie-based affinity disabled.
The settings are stored in the $Setting variable.

## PARAMETERS

### -CookieBasedAffinity
Specifies whether cookie-based affinity should be enabled or disabled for the back-end server pool.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Enabled, Disabled

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the back-end HTTP settings that this cmdlet creates.

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

### -Port
Specifies the port of the back-end server pool.

```yaml
Type: Int32
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

### -Protocol
Specifies the protocol to use for communication between the application gateway and the back-end servers.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayBackendHttpSettings](.\Add-AzureApplicationGatewayBackendHttpSettings.md)

[Get-AzureApplicationGatewayBackendHttpSettings](.\Get-AzureApplicationGatewayBackendHttpSettings.md)

[Remove-AzureApplicationGatewayBackendHttpSettings](.\Remove-AzureApplicationGatewayBackendHttpSettings.md)

[Set-AzureApplicationGatewayBackendHttpSettings](.\Set-AzureApplicationGatewayBackendHttpSettings.md)

