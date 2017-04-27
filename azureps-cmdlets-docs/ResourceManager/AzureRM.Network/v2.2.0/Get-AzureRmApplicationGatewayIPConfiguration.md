---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApplicationGatewayIPConfiguration

## SYNOPSIS
Gets the IP configuration of an application gateway.

## SYNTAX

```
Get-AzureRmApplicationGatewayIPConfiguration [-Name <String>] -ApplicationGateway <PSApplicationGateway>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Get-AzureRmApplicationGatewayIPConfiguration cmdlet gets the IP configuration of an application gateway.
The IP configuration contains the subnet in which the application gateway is deployed.

## EXAMPLES

### --------------------------  Example 1: Get a specific IP configuration  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\>$AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $GatewaySubnet = Get-AzureRmApplicationGatewayIPConfiguration -Name "GatewaySubnet01" -ApplicationGateway $AppGw
```

The first command gets an application gateway and stores it in the $AppGw variable.

### --------------------------  Example 2: Get a list of IP configurations  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\>$AppGw = Get-AzureRmApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $GatewaySubnets = Get-AzureRmApplicationGatewayIPConfiguration -ApplicationGateway $AppGw
```

The first command gets an application gateway and stores it in the $AppGw variable.

## PARAMETERS

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration

### IEnumerable<Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration>

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzureRmApplicationGatewayIPConfiguration]()

[New-AzureRmApplicationGatewayIPConfiguration]()

[Remove-AzureRmApplicationGatewayIPConfiguration]()

[Set-AzureRmApplicationGatewayIPConfiguration]()

