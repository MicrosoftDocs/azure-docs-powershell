---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmApplicationGatewayIPConfiguration

## SYNOPSIS
Removes an IP configuration from an application gateway.

## SYNTAX

```
Remove-AzureRmApplicationGatewayIPConfiguration -Name <String> -ApplicationGateway <PSApplicationGateway>
 [<CommonParameters>]
```

## DESCRIPTION
The Remove-AzureRmApplicationGatewayIPConfiguration cmdlet removes an IP configuration from an Azure application gateway.

## EXAMPLES

### --------------------------  Example 1: Remove an IP configuration from an azure_2 application gateway.  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\>$AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> Remove-AzureRmApplicationGatewayIPConfiguration -ApplicationGateway $AppGw -Name "Subnet02"
```

The first command gets an application gateway and stores it in the $AppGw variable.

## PARAMETERS

### -Name
Specifies the name of the IP configuration to remove.

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

### -ApplicationGateway
Specifies the application gateway from which to remove an IP configuration.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayIPConfiguration]()

[Get-AzureRmApplicationGatewayIPConfiguration]()

[New-AzureRmApplicationGatewayIPConfiguration]()

[Set-AzureRmApplicationGatewayIPConfiguration]()

