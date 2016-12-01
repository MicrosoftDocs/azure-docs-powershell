---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2BD0BE95-EC07-46B9-B674-CEA71F9FA4A9
---

# Get-AzureRmApplicationGatewayHttpListener

## SYNOPSIS
Gets the HTTP listener of an application gateway.

## SYNTAX

```
Get-AzureRmApplicationGatewayHttpListener [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApplicationGatewayHttpListener** cmdlet gets the HTTP listener of an application gateway.

## EXAMPLES

### Example 1: Get a specific HTTP listener
```
PS C:\>$Appgw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Listener = Get-AzureRmApplicationGatewayHttpListener -Name "Listener01" -ApplicationGateway $Appgw
```

This command gets an HTTP listener named Listener01.

### Example 2: Get a list of HTTP listeners
```
PS C:\>$Appgw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Listeners = Get-AzureRmApplicationGatewayHttpListener -ApplicationGateway $Appgw
```

This command gets a list of HTTP listeners.

## PARAMETERS

### -Name
Specifies the name of the HTTP listener which this cmdlet gets.

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

### -ApplicationGateway
Specifies the application gateway object that contains the HTTP listener.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener

## NOTES

## RELATED LINKS

[Add-AzureRmApplicationGatewayHttpListener](./Add-AzureRmApplicationGatewayHttpListener.md)

[New-AzureRmApplicationGatewayHttpListener](./New-AzureRmApplicationGatewayHttpListener.md)

[Remove-AzureRmApplicationGatewayHttpListener](./Remove-AzureRmApplicationGatewayHttpListener.md)

[Set-AzureRmApplicationGatewayHttpListener](./Set-AzureRmApplicationGatewayHttpListener.md)


