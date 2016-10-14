---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayFrontendPort.md
schema: 2.0.0
---

# Get-AzureApplicationGatewayFrontendPort

## SYNOPSIS
Gets the front-end port of an application gateway.

## SYNTAX

```
Get-AzureApplicationGatewayFrontendPort [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureApplicationGatewayFrontendPort** cmdlet gets the front-end port of an application gateway.

## EXAMPLES

### 1: Get a specified front-end port
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndPort = Get-AzureApplicationGatewayFrontendIPort -Name "FrontEndPort01" -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

The second command gets the front-end port named FrontEndPort01 from $AppGw and stores it in the $FrontEndPort variable.

### 2: Get a list of front-end ports
```
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndPorts = Get-AzureApplicationGatewayFrontendIPort  -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

The second command gets a list of the front-end ports from $AppGw and stores it in the $FrontEndPorts variable.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway object that contains the front-end port.

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
Specifies the name of the front-end port to get.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort>

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayFrontendPort](.\Add-AzureApplicationGatewayFrontendPort.md)

[New-AzureApplicationGatewayFrontendPort](.\New-AzureApplicationGatewayFrontendPort.md)

[Remove-AzureApplicationGatewayFrontendPort](.\Remove-AzureApplicationGatewayFrontendPort.md)

[Set-AzureApplicationGatewayFrontendPort](.\Set-AzureApplicationGatewayFrontendPort.md)

