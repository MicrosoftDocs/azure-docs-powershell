---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApplicationGatewayFrontendPort

## SYNOPSIS
Gets the front-end port of an application gateway.

## SYNTAX

```
Get-AzureRmApplicationGatewayFrontendPort [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Get-AzureRmApplicationGatewayFrontendPort cmdlet gets the front-end port of an application gateway.

## EXAMPLES

### --------------------------  1: Get a specified frontend port  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndPort = Get-AzureRmApplicationGatewayFrontendIPort -Name "FrontEndPort01" -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

### --------------------------  2: Get a list of frontend ports  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> $AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $FrontEndPorts = Get-AzureRmApplicationGatewayFrontendIPort  -ApplicationGateway $AppGw
```

The first command gets an application gateway named ApplicationGateway01 from the resource group named ResourceGroup01, and stores it in the $AppGw variable.

## PARAMETERS

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort>

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayFrontendPort]()

[New-AzureRmApplicationGatewayFrontendPort]()

[Remove-AzureRmApplicationGatewayFrontendPort]()

[Set-AzureRmApplicationGatewayFrontendPort]()

