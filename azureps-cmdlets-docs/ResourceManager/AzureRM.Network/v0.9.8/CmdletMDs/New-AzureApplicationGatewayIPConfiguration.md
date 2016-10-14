---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\Add-AzureApplicationGatewayIPConfiguration.md
schema: 2.0.0
---

# New-AzureApplicationGatewayIPConfiguration

## SYNOPSIS
Creates an IP configuration for an application gateway.

## SYNTAX

### SetByResourceId
```
New-AzureApplicationGatewayIPConfiguration -Name <String> [-SubnetId <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### SetByResource
```
New-AzureApplicationGatewayIPConfiguration -Name <String> [-Subnet <PSSubnet>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGatewayIPConfiguration** cmdlet creates an IP configuration for an application gateway.
The IP configuration contains the subnet in which application gateway is deployed.

## EXAMPLES

### Example 1: Create an IP configuration for an application gateway.
```
PS C:\>$VNet = Get-AzurevirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureVirtualNetworkSubnetConfig -Name "Subnet01" -VirtualNetwork $VNet 
PS C:\ $GatewayIpConfig = New-AzureApplicationGatewayIPConfiguration -Name "AppGwSubnet01" -Subnet $Subnet
```

The first command gets a virtual network named VNet01 that belongs to the resource group named ResourceGroup01.

The second command gets the subnet configuration for the subnet that the virtual network in the previous command belongs to, and stores it in the $Subnet variable.

The third command creates the IP configuration using $Subnet.

## PARAMETERS

### -Name
Specifies the name of the IP configuration to create.

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
Specifies the subnet object.
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
Specifies the subnet ID.
This is the subnet in which the application gateway would be deployed.

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration

## NOTES

## RELATED LINKS

[Add-AzureApplicationGatewayIPConfiguration](.\Add-AzureApplicationGatewayIPConfiguration.md)

[Get-AzureApplicationGatewayIPConfiguration](.\Get-AzureApplicationGatewayIPConfiguration.md)

[Remove-AzureApplicationGatewayIPConfiguration](.\Remove-AzureApplicationGatewayIPConfiguration.md)

[Set-AzureApplicationGatewayIPConfiguration](.\Set-AzureApplicationGatewayIPConfiguration.md)

