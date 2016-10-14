---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayIPConfiguration.md
schema: 2.0.0
---

# Get-AzureApplicationGatewayIPConfiguration

## SYNOPSIS
Gets the IP configuration of an application gateway.

## SYNTAX

```
Get-AzureApplicationGatewayIPConfiguration [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGatewayIPConfiguration** cmdlet gets the IP configuration of an application gateway.
The IP configuration contains the subnet in which the application gateway is deployed.

## EXAMPLES

### Example 1: Get a specific IP configuration
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $GatewaySubnet = Get-AzureApplicationGatewayIPConfiguration -Name "GatewaySubnet01" -ApplicationGateway $AppGw
```

The first command gets an application gateway and stores it in the $AppGw variable.

The second command gets an IP configuration named GateSubnet01 from the gateway stored in $AppGw.

### Example 2: Get a list of IP configurations
```
PS C:\>$AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $GatewaySubnets = Get-AzureApplicationGatewayIPConfiguration -ApplicationGateway $AppGw
```

The first command gets an application gateway and stores it in the $AppGw variable.

The second command gets a list of all IP configurations.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway object that contains IP configuration.

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

### -Name
Specifies the name of the IP configuration which this cmdlet gets.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration>

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayIPConfiguration](.\Add-AzureApplicationGatewayIPConfiguration.md)

[New-AzureApplicationGatewayIPConfiguration](.\New-AzureApplicationGatewayIPConfiguration.md)

[Remove-AzureApplicationGatewayIPConfiguration](.\Remove-AzureApplicationGatewayIPConfiguration.md)

[Set-AzureApplicationGatewayIPConfiguration](.\Set-AzureApplicationGatewayIPConfiguration.md)

