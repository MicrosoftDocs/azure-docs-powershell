---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayRequestRoutingRule.md
schema: 2.0.0
---

# New-AzureApplicationGatewayRequestRoutingRule

## SYNOPSIS
Creates a request routing rule for an application gateway.

## SYNTAX

### SetByResourceId
```
New-AzureApplicationGatewayRequestRoutingRule -Name <String> -RuleType <String>
 [-BackendHttpSettingsId <String>] [-HttpListenerId <String>] [-BackendAddressPoolId <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetByResource
```
New-AzureApplicationGatewayRequestRoutingRule -Name <String> -RuleType <String>
 [-BackendHttpSettings <PSApplicationGatewayBackendHttpSettings>]
 [-HttpListener <PSApplicationGatewayHttpListener>]
 [-BackendAddressPool <PSApplicationGatewayBackendAddressPool>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureApplicationGatewayRequestRoutingRule** cmdlet creates a request routing rule for an Azure application gateway.

## EXAMPLES

### Example 1: Create a request routing rule for an application gateway
```
PS C:\>$Rule = New-AzureApplicationGatewayRequestRoutingRule -Name "Rule01" -RuleType Basic -BackendHttpSettings $Setting -HttpListener $Listener -BackendAddressPool $Pool
```

This command creates a request routing rule.

## PARAMETERS

### -BackendAddressPool
Specifies the back-end address pool (as an object) for the request routing rule to create.

```yaml
Type: PSApplicationGatewayBackendAddressPool
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendAddressPoolId
Specifies the back-end address pool (as an ID) of the request routing rule to create.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendHttpSettings
Specifies the back-end HTTP settings (as object) for the request routing rule to create.

```yaml
Type: PSApplicationGatewayBackendHttpSettings
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendHttpSettingsId
Specifies the back-end HTTP settings (as an ID) of the request routing rule to create.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpListener
Specifies the back-end HTTP listener (as an object) for the request routing rule to create.

```yaml
Type: PSApplicationGatewayHttpListener
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpListenerId
Specifies the backend HTTP listener (as an ID) for the request routing rule to create.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the request routing rule to create.

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

### -RuleType
Specifies type of the request routing rule.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayRequestRoutingRule](.\Add-AzureApplicationGatewayRequestRoutingRule.md)

[Get-AzureApplicationGatewayRequestRoutingRule](.\Get-AzureApplicationGatewayRequestRoutingRule.md)

[Remove-AzureApplicationGatewayRequestRoutingRule](.\Remove-AzureApplicationGatewayRequestRoutingRule.md)

[Set-AzureApplicationGatewayRequestRoutingRule](.\Set-AzureApplicationGatewayRequestRoutingRule.md)

