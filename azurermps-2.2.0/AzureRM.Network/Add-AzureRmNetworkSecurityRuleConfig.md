---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRmNetworkSecurityRuleConfig

## SYNOPSIS
Adds a network security rule configuration to a network security group.

## SYNTAX

```
Add-AzureRmNetworkSecurityRuleConfig -Name <String> -NetworkSecurityGroup <PSNetworkSecurityGroup>
 [-Description <String>] [-Protocol <String>] [-SourcePortRange <String>] [-DestinationPortRange <String>]
 [-SourceAddressPrefix <String>] [-DestinationAddressPrefix <String>] [-Access <String>] [-Priority <Int32>]
 [-Direction <String>] [<CommonParameters>]
```

## DESCRIPTION
The Add-AzureRmNetworkSecurityRuleConfig cmdlet adds a network security rule configuration to an Azure network security group.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}





```
Get-AzureRmNetworkSecurityGroup -Name  nsg1 -ResourceGroupName rg1 | Add-AzureRmNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389 | Set-AzureRmNetworkSecurityGroup
```

Retrieves an Azure network security group named "nsg1" from resource group "rg1".
Adds a network security rule named "rdp-rule" that allows traffic from internet on port 3389 to the retrieved network security group object.
Persists the modified Azure network security group.

Name                 : nsg1
ResourceGroupName    : rg1
Location             : westus
Id                   : /subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Microsoft.Netwo
                       rk/networkSecurityGroups/nsg1
Etag                 : W/"d98c20b0-c764-45e8-98bd-f0afa1d9e73b"
ResourceGuid         : 91e36ce0-8640-41db-a2b9-20e8a17e167c
ProvisioningState    : Succeeded
Tags                 :
SecurityRules        : \[
                         {
                           "Name": "rdp-rule",
                           "Etag": "W/\"d98c20b0-c764-45e8-98bd-f0afa1d9e73b\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/nsg1/securityRules/rdp-rule",
                           "Description": "Allow RDP",
                           "Protocol": "Tcp",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "3389",
                           "SourceAddressPrefix": "Internet",
                           "DestinationAddressPrefix": "*",
                           "Access": "Allow",
                           "Priority": 100,
                           "Direction": "Inbound",
                           "ProvisioningState": "Succeeded"
                         }
                       \]
DefaultSecurityRules : \[
                         {
                           "Name": "AllowVnetInBound",
                           "Etag": "W/\"d98c20b0-c764-45e8-98bd-f0afa1d9e73b\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/AllowVnetInBound",
                           "Description": "Allow inbound traffic from all VMs in VNET",
                           "Protocol": "*",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "*",
                           "SourceAddressPrefix": "VirtualNetwork",
                           "DestinationAddressPrefix": "VirtualNetwork",
                           "Access": "Allow",
                           "Priority": 65000,
                           "Direction": "Inbound",
                           "ProvisioningState": "Succeeded"
                         },
                         {
                           "Name": "AllowAzureLoadBalancerInBound",
                           "Etag": "W/\"d98c20b0-c764-45e8-98bd-f0afa1d9e73b\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/AllowAzureLoadBalancerInBound",
                           "Description": "Allow inbound traffic from azure load balancer",
                           "Protocol": "*",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "*",
                           "SourceAddressPrefix": "AzureLoadBalancer",
                           "DestinationAddressPrefix": "*",
                           "Access": "Allow",
                           "Priority": 65001,
                           "Direction": "Inbound",
                           "ProvisioningState": "Succeeded"
                         },
                         {
                           "Name": "DenyAllInBound",
                           "Etag": "W/\"d98c20b0-c764-45e8-98bd-f0afa1d9e73b\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/DenyAllInBound",
                           "Description": "Deny all inbound traffic",
                           "Protocol": "*",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "*",
                           "SourceAddressPrefix": "*",
                           "DestinationAddressPrefix": "*",
                           "Access": "Deny",
                           "Priority": 65500,
                           "Direction": "Inbound",
                           "ProvisioningState": "Succeeded"
                         },
                         {
                           "Name": "AllowVnetOutBound",
                           "Etag": "W/\"d98c20b0-c764-45e8-98bd-f0afa1d9e73b\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/AllowVnetOutBound",
                           "Description": "Allow outbound traffic from all VMs to all VMs in VNET",
                           "Protocol": "*",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "*",
                           "SourceAddressPrefix": "VirtualNetwork",
                           "DestinationAddressPrefix": "VirtualNetwork",
                           "Access": "Allow",
                           "Priority": 65000,
                           "Direction": "Outbound",
                           "ProvisioningState": "Succeeded"
                         },
                         {
                           "Name": "AllowInternetOutBound",
                           "Etag": "W/\"d98c20b0-c764-45e8-98bd-f0afa1d9e73b\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/AllowInternetOutBound",
                           "Description": "Allow outbound traffic from all VMs to Internet",
                           "Protocol": "*",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "*",
                           "SourceAddressPrefix": "*",
                           "DestinationAddressPrefix": "Internet",
                           "Access": "Allow",
                           "Priority": 65001,
                           "Direction": "Outbound",
                           "ProvisioningState": "Succeeded"
                         },
                         {
                           "Name": "DenyAllOutBound",
                           "Etag": "W/\"d98c20b0-c764-45e8-98bd-f0afa1d9e73b\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/DenyAllOutBound",
                           "Description": "Deny all outbound traffic",
                           "Protocol": "*",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "*",
                           "SourceAddressPrefix": "*",
                           "DestinationAddressPrefix": "*",
                           "Access": "Deny",
                           "Priority": 65500,
                           "Direction": "Outbound",
                           "ProvisioningState": "Succeeded"
                         }
                       \]
NetworkInterfaces    : \[\]
Subnets              : \[\]

## PARAMETERS

### -Name
Specifies the name of a network security rule configuration.

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

### -NetworkSecurityGroup
Specifies a NetworkSecurityGroup object.
This cmdlet adds a network security rule configuration to the object that this parameter specifies.

```yaml
Type: PSNetworkSecurityGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
Specifies a description of a network security rule configuration.

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

### -Protocol
Specifies the network protocol that a rule configuration applies to.
The acceptable values for this parameter are:

-- Tcp
-- Udp
-- Wildcard character (*) to match both

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

### -SourcePortRange
Specifies a source port or range.
This value is expressed as an integer, as a range between 0 and 65535, or as a wildcard character (*) to match any source port.

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

### -DestinationPortRange
Specifies a destination port or range.
The acceptable values for this parameter are:

-- An integer
-- A range of integers between 0 and 65535
-- A wildcard character (*) to match any port

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

### -SourceAddressPrefix
Specifies a source address prefix.
The acceptable values for this parameter are:

-- A CIDR
-- A source IP range
-- A wildcard character (*) to match any IP address.

You can also use tags such as VirtualNetwork, AzureLoadBalancer and Internet.

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

### -DestinationAddressPrefix
Specifies a destination address prefix.
The acceptable values for this parameter are:

-- A Classless Interdomain Routing (CIDR) address
-- A destination IP address range
-- A wildcard character (*) to match any IP address

You can use tags such as VirtualNetwork, AzureLoadBalancer, and Internet.

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

### -Access
Specifies whether network traffic is allowed or denied.
The acceptable values for this parameter are:Allow and Deny.

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

### -Priority
Specifies the priority of a rule configuration.
The acceptable values for this parameter are:An integer between 100 and 4096.

The priority number must be unique for each rule in the collection.
The lower the priority number, the higher the priority of the rule.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Direction
Specifies whether a rule is evaluated on incoming or outgoing traffic.
The acceptable values for this parameter are:Inbound and Outbound.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmNetworkSecurityRuleConfig]()

[New-AzureRmNetworkSecurityRuleConfig]()

[Remove-AzureRmNetworkSecurityRuleConfig]()

[Set-AzureRmNetworkSecurityRuleConfig]()

