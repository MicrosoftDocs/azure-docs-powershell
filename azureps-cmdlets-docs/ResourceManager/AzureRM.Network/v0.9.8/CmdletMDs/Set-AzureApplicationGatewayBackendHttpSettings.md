---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayBackendHttpSettings.md
schema: 2.0.0
---

# Set-AzureApplicationGatewayBackendHttpSettings

## SYNOPSIS
Updates back-end HTTP settings for an application gateway.

## SYNTAX

```
Set-AzureApplicationGatewayBackendHttpSettings -ApplicationGateway <PSApplicationGateway> -Name <String>
 -Port <Int32> -Protocol <String> -CookieBasedAffinity <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureApplicationGatewayBackendHttpSettings** cmdlet updates the back-end Hypertext Transfer Protocol (HTTP) settings for an Azure application gateway.
Back-end HTTP settings are applied to all back-end servers in a pool.

## EXAMPLES

### Example 1: Update the back-end HTTP settings for an application gateway
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzureApplicationGatewayBackendHttpSettings -ApplicationGateway $AppGw 
-Name "Setting02" -Port 88 -Protocol "Http" -CookieBasedAffinity "Disabled"
```

The first command gets the application gateway named ApplicationGateway01 that belongs to the resource group named ResourceGroup01 and stores it in the $AppGw variable.

The second command updates the HTTP settings of the application gateway in $AppGw to use port 88, the HTTP protocol and enables cookie-based affinity.

## PARAMETERS

### -ApplicationGateway
Specifies an application gateway object with which this cmdlet associates back-end HTTP settings.

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CookieBasedAffinity
Specifies whether cookie-based affinity should be enabled or disabled for the backend server pool.
The acceptable values for this parameter are: Disabled, Enabled.

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
Specifies the name of the back-end HTTP settings object.

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
Specifies the port to use for each server in the back-end server pool.

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
Specifies the protocol to use for communication between the application gateway and back-end servers.
The acceptable values for this parameter are: Http.
This parameter is case-sensitive.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayBackendHttpSettings](.\Add-AzureApplicationGatewayBackendHttpSettings.md)

[Get-AzureApplicationGatewayBackendHttpSettings](.\Get-AzureApplicationGatewayBackendHttpSettings.md)

[New-AzureApplicationGatewayBackendHttpSettings](.\New-AzureApplicationGatewayBackendHttpSettings.md)

[Remove-AzureApplicationGatewayBackendHttpSettings](.\Remove-AzureApplicationGatewayBackendHttpSettings.md)

