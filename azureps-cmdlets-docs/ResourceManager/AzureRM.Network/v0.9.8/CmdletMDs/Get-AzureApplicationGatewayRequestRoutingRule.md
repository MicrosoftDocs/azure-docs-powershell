---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayRequestRoutingRule.md
schema: 2.0.0
---

# Get-AzureApplicationGatewayRequestRoutingRule

## SYNOPSIS
Gets the request routing rule of an application gateway.

## SYNTAX

```
Get-AzureApplicationGatewayRequestRoutingRule [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGatewayRequestRoutingRule** cmdlet gets the request routing rule of an application gateway.

## EXAMPLES

### Example 1: Get a specific request routing rule
```
PS C:\>$AppGW = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Rule = Get-AzureApplicationGatewayRequestRoutingRule -"Rule01" -ApplicationGateway $AppGW
```

This command gets the request routing rule named Rule01.

### Example 2: Get a list of request routing rules
```
PS C:\>$AppGW = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Rules = Get-AzureApplicationGatewayRequestRoutingRule -ApplicationGateway $AppGW
```

This command gets a list of request routing rules.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway object that contains request routing rule.

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
Specifies the name of the request routing rule which this cmdlet gets.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule>

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayRequestRoutingRule](.\Add-AzureApplicationGatewayRequestRoutingRule.md)

[New-AzureApplicationGatewayRequestRoutingRule](.\New-AzureApplicationGatewayRequestRoutingRule.md)

[Remove-AzureApplicationGatewayRequestRoutingRule](.\Remove-AzureApplicationGatewayRequestRoutingRule.md)

[Set-AzureApplicationGatewayRequestRoutingRule](.\Set-AzureApplicationGatewayRequestRoutingRule.md)

