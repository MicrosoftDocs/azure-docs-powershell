---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApplicationGatewayFrontendIPConfig

## SYNOPSIS
Gets the front-end IP configuration of an application gateway.

## SYNTAX

```
Get-AzureRmApplicationGatewayFrontendIPConfig [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Get-AzureRmApplicationGatewayFrontendIPConfig cmdlet gets the front-end IP configuration of an application gateway.

## EXAMPLES

### --------------------------  Example 1: Get a specified frontend IP configuration  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndIP= Get-AzureRmApplicationGatewayFrontendIPConfig -Name "FrontEndIP01" -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

### --------------------------  Example 2: Get a list of frontend IP configurations  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndIPs= Get-AzureRmApplicationGatewayFrontendIPConfig  -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

## PARAMETERS

### -Name
Specifies the name of the front-end IP configuration that this cmdlet gets.

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
Specifies the application gateway object that contains the front-end IP configuration.

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

### -InformationAction
@{Text=}

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration>

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayFrontendIPConfig]()

[New-AzureRmApplicationGatewayFrontendIPConfig]()

[Remove-AzureRmApplicationGatewayFrontendIPConfig]()

[Set-AzureRmApplicationGatewayFrontendIPConfig]()

