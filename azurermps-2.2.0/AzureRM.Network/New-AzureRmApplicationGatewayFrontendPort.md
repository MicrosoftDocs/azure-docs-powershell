---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmApplicationGatewayFrontendPort

## SYNOPSIS
Creates a front-end port for an application gateway.

## SYNTAX

```
New-AzureRmApplicationGatewayFrontendPort -Name <String> -Port <Int32> [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmApplicationGatewayFrontendPort cmdlet creates a front-end port for an Azure application gateway.

## EXAMPLES

### --------------------------  Example1: Create a frontend port  --------------------------
@{paragraph=PS C:\\\>}





```
PS C:\> $FrontEndPort = New-AzureRmApplicationGatewayFrontendPort -Name "FrontEndPort01" -Port 80
```

This command creates a front-end port on port 80 named FrontEndPort01.

## PARAMETERS

### -Name
Specifies the name of the front-end port that this cmdlet creates.

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
Specifies the port number of the front-end port.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayFrontendPort]()

[Get-AzureRmApplicationGatewayFrontendPort]()

[Remove-AzureRmApplicationGatewayFrontendPort]()

[Set-AzureRmApplicationGatewayFrontendPort]()

