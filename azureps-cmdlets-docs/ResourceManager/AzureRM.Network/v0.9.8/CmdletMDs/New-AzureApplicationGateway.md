---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: .\New-AzureApplicationGatewayBackendAddressPool.md
schema: 2.0.0
---

# New-AzureApplicationGateway

## SYNOPSIS
Creates an application gateway.

## SYNTAX

```
New-AzureApplicationGateway -Name <String> -ResourceGroupName <String> -Location <String>
 -Sku <PSApplicationGatewaySku>
 -GatewayIPConfigurations <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration]>
 [-SslCertificates <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate]>]
 [-FrontendIPConfigurations <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration]>]
 -FrontendPorts <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort]>
 -BackendAddressPools <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool]>
 -BackendHttpSettingsCollection <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings]>
 -HttpListeners <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener]>
 -RequestRoutingRules <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule]>
 [-Tag <Hashtable[]>] [-Force] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureApplicationGateway** cmdlet creates an Azure application gateway.

An application gateway requires the following: 

- A resource group.
- A virtual network. 
- A back-end server pool, containing the IP addresses of the back-end servers.
- Back-end server pool settings.
Each pool has settings such as port, protocol and cookie-based affinity, that are applied to all servers within the pool.
- Front-end IP addresses, which are the IP addresses opened on the application gateway.
A front-end IP address can be a public IP address or an internal IP address.
- Front-end ports, which are the public ports opened on the application gateway.
Traffic that hits these ports is redirected to the back-end servers. 
- A request routing rule that binds the listener and the back-end server pool.
The rule defines which back-end server pool the traffic should be directed to when it hits a particular listener.
A listener has a front-end port, front-end IP address, protocol (http or https) and Secure Sockets Layer (SSL) certificate name (if configuring SSL offload).

## EXAMPLES

### Example 1: Create an application gateway
```
This command creates a resource group for the application gateway.
PS C:\> $ResourceGroup = New-AzureResourceGroup -Name "ResourceGroup01" -Location "West US" -Tags @{Name = "Department"; Value = "Marketing"}

These four commands create a virtual network. The first command creates a subnet configuration. The second command creates a virtual network. The third command verifies the subnet configuration and the fourth command verifies that the virtual network is created successfully.
PS C:\> $Subnet = New-AzureVirtualNetworkSubnetConfig -Name "Subnet01" -AddressPrefix 10.0.0.0/24
PS C:\> $VNet = New-AzurevirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01" -Location "West US" -AddressPrefix 10.0.0.0/16 -Subnet $Subnet
PS C:\> $VNet = Get-AzurevirtualNetwork -Name "VNet01" -ResourceGroupName "ResourceGroup01"
PS C:\> $Subnet = Get-AzureVirtualNetworkSubnetConfig -Name $Subnet01 -VirtualNetwork $VNet

The following commands create the application gateway.The first command creates an IP configuration named GatewayIp01 for the subnet created previously.The second command creates a back-end server pool named Pool01 with a list of back-end IP addresses and stores the pool in the $Pool variable.The third command creates the settings for the back-end server pool and stores the settings in the $PoolSetting variable.The forth command creates a front-end port on port 80, names it FrontEndPort01, and stores the port in the $FrontEndPort variable.The fifth command creates a public IP address by using **New-AzurePublicIpAddress**. The sixth command creates a front-end IP configuration using $PublicIp, names it FrontEndPortConfig01, and stores it in the $FrontEndIpConfig variable.The seventh command creates a listener using the previously created $FrontEndIpConfig $FrontEndPort.The eighth command creates a rule for the listener.The ninth command sets the SKU.The tenth command creates the gateway using the objects set by the previous commands.
PS C:\> $GatewayIPconfig = New-AzureApplicationGatewayIPConfiguration -Name "GatewayIp01" -Subnet $Subnet
PS C:\> $Pool = New-AzureApplicationGatewayBackendAddressPool -Name "Pool01" -BackendIPAddresses 10.10.10.1, 10.10.10.2, 10.10.10.3
PS C:\> $PoolSetting = New-AzureApplicationGatewayBackendHttpSettings -Name "PoolSetting01"  -Port 80 -Protocol "Http" -CookieBasedAffinity "Disabled"
PS C:\> $FrontEndPort = New-AzureApplicationGatewayFrontendPort -Name "FrontEndPort01"  -Port 80
# Create a public IP address
PS C:\> $PublicIp = New-AzurePublicIpAddress -ResourceGroupName "ResourceGroup01" -Name $PublicIpName -Location "West US" -AllocationMethod "Dynamic"
PS C:\> $FrontEndIpConfig = New-AzureApplicationGatewayFrontendIPConfig -Name "FrontEndConfig01" -PublicIPAddress $PublicIp
PS C:\> $Listener = New-AzureApplicationGatewayHttpListener -Name $listenerName  -Protocol "Http" -FrontendIpConfiguration $FrontEndIpConfig -FrontendPort $ FrontEndPort
PS C:\> $Rule = New-AzureApplicationGatewayRequestRoutingRule -Name "Rule01" -RuleType basic -BackendHttpSettings $PoolSetting -HttpListener $Listener -BackendAddressPool $Pool
PS C:\> $Sku = New-AzureApplicationGatewaySku -Name "Standard_Small" -Tier Standard -Capacity 2
PS C:\> $Gateway = New-AzureApplicationGateway -Name "AppGateway01" -ResourceGroupName "ResourceGroup01" -Location "West US" -BackendAddressPools $Pool -BackendHttpSettingsCollection $PoolSetting -FrontendIpConfigurations $FrontEndIpConfig  -GatewayIpConfigurations $GatewayIpConfig -FrontendPorts $FrontEndPort -HttpListeners $Listener -RequestRoutingRules $Rule -Sku $Sku
```

The following commands create an application gateway by first creating a resource group and a virtual network, as well as the following: 

- A back-end server pool
- Back-end server pool settings
- Front-end ports
- Front-end IP addresses
- A request routing rule

## PARAMETERS

### -BackendAddressPools
Specifies the list of back-end address pools for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackendHttpSettingsCollection
Specifies the list of back-end HTTP settings for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the creation of the application gateway even if an application gateway with the same name already exists.```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendIPConfigurations
Specifies a list of front-end IP configurations for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendIPConfiguration]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FrontendPorts
Specifies a list of front-end ports for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFrontendPort]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GatewayIPConfigurations
Specifies a list of IP configurations for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayIPConfiguration]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HttpListeners
Specifies a list of HTTP listeners for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayHttpListener]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the region in which to create the application gateway.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of application gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -RequestRoutingRules
Specifies a list of request routing rules for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRequestRoutingRule]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group in which to create the application gateway.```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Specifies the stock keeping unit (SKU) of the application gateway.```yaml
Type: PSApplicationGatewaySku
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SslCertificates
Specifies the list of Secure Sockets Layer (SSL) certificates for the application gateway.```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslCertificate]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies the dictionary of tags associated with the application gateway.```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## NOTES

## RELATED LINKS

[New-AzureApplicationGatewayBackendAddressPool](.\New-AzureApplicationGatewayBackendAddressPool.md)

[New-AzureApplicationGatewayBackendHttpSettings](.\New-AzureApplicationGatewayBackendHttpSettings.md)

[New-AzureApplicationGatewayFrontendIPConfig](.\New-AzureApplicationGatewayFrontendIPConfig.md)

[New-AzureApplicationGatewayFrontendPort](.\New-AzureApplicationGatewayFrontendPort.md)

[New-AzureApplicationGatewayHttpListener](.\New-AzureApplicationGatewayHttpListener.md)

[New-AzureApplicationGatewayIPConfiguration](.\New-AzureApplicationGatewayIPConfiguration.md)

[New-AzureApplicationGatewayRequestRoutingRule](.\New-AzureApplicationGatewayRequestRoutingRule.md)

[New-AzureApplicationGatewaySku](.\New-AzureApplicationGatewaySku.md)

[New-AzureVirtualNetwork](.\New-AzureVirtualNetwork.md)

[New-AzureVirtualNetworkSubnetConfig](.\New-AzureVirtualNetworkSubnetConfig.md)

