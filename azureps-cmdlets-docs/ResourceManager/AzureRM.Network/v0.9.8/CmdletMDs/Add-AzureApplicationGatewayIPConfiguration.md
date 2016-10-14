---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Get-AzureApplicationGatewayIPConfiguration.md
schema: 2.0.0
---

# Add-AzureApplicationGatewayIPConfiguration

## SYNOPSIS
Adds an IP configuration to an application gateway.

## SYNTAX

### SetByResourceId
```
Add-AzureApplicationGatewayIPConfiguration -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-SubnetId <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### SetByResource
```
Add-AzureApplicationGatewayIPConfiguration -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-Subnet <PSSubnet>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureApplicationGatewayIPConfiguration** cmdlet adds an IP configuration to an application gateway.
IP configurations contain the subnet in which the application gateway is deployed.

## EXAMPLES

### Example 1: Add an virtual network configuration to an application gateway
```
PS C:\>$Vnet = Get-AzureVirtualNetwork -Name "Vnet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $Vnet 
PS C:\> $AppGw = Get-AzureApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Add-AzureApplicationGatewayIPConfiguration -ApplicationGateway $AppGw -Name "Appgwsubnet01" -Subnet $Subnet
```

The first command creates a virtual network.

The second command creates a subnet using the previously created virtual network.

The third command gets the application gateway and stores it in the $AppGw variable.

The fouth command adds the IP configuration to the application gateway stored in $AppGw.

## PARAMETERS

### -ApplicationGateway
Specifies the application gateway to which this cmdlet adds an IP configuration.

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
Specifies the name of the IP configuration to add.

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

### -Subnet
Specifies a subnet.
This is the subnet in which the application gateway is deployed.

```yaml
Type: PSSubnet
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Specifies a subnet ID.
This is the subnet in which the application gateway is deployed.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSSubnet

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[Get-AzureApplicationGatewayIPConfiguration](.\Get-AzureApplicationGatewayIPConfiguration.md)

[New-AzureApplicationGatewayIPConfiguration](.\New-AzureApplicationGatewayIPConfiguration.md)

[Remove-AzureApplicationGatewayIPConfiguration](.\Remove-AzureApplicationGatewayIPConfiguration.md)

[Set-AzureApplicationGatewayIPConfiguration](.\Set-AzureApplicationGatewayIPConfiguration.md)

