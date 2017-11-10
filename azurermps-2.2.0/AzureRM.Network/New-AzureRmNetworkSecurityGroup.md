---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmNetworkSecurityGroup

## SYNOPSIS
Creates a network security group.

## SYNTAX

```
New-AzureRmNetworkSecurityGroup -Name <String> -ResourceGroupName <String> -Location <String>
 [-SecurityRules <System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSSecurityRule]>]
 [-Tag <Hashtable[]>] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmNetworkSecurityGroup cmdlet creates an  Azure network security group.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}





```
New-AzureRmNetworkSecurityGroup -Name "nsg1" -ResourceGroupName "rg1"  -Location  "westus"
```

Creates a new Azure network security group named "nsg1" in resource group "rg1" in location "westus".

Name                 : nsg1
ResourceGroupName    : rg1
Location             : westus
Id                   : /subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Microsoft.Network/networkSecurityGroups/nsg1
Etag                 : W/"b4833539-3f97-4c90-ab00-8521d7f5ca35"
ResourceGuid         : 91e36ce0-8640-41db-a2b9-20e8a17e167c
ProvisioningState    : Succeeded
Tags                 :
SecurityRules        : \[\]
DefaultSecurityRules : \[
                         {
                           "Name": "AllowVnetInBound",
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
                           "Id": "/subscriptions/9532a63e-f2eb-4649-bb23-5ed01077ce80/resourceGroups/rg1/providers/Microsoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/AllowVnetInBound",
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
                           "Id": "/subscriptions/9532a63e-f2eb-4649-bb23-5ed01077ce80/resourceGroups/rg1/providers/Microsoft.Network/networkSecurityGroups/nsg1/defaultSecurityRules/AllowAzureLoadBalancerInBound",
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
                           "Id": "/subscriptions/9532a63e-f2eb-4649-bb23-5ed01077ce80/resourceGroups/rg1/providers/Micr
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
                           "Id": "/subscriptions/9532a63e-f2eb-4649-bb23-5ed01077ce80/resourceGroups/rg1/providers/Micr
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
                           "Id": "/subscriptions/9532a63e-f2eb-4649-bb23-5ed01077ce80/resourceGroups/rg1/providers/Micr
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
                           "Id": "/subscriptions/9532a63e-f2eb-4649-bb23-5ed01077ce80/resourceGroups/rg1/providers/Micr
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

### --------------------------  Example 2  --------------------------
@{paragraph=PS C:\\\>}





```
$rule1 = New-AzureRmNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389

$rule2 = New-AzureRmNetworkSecurityRuleConfig -Name web-rule -Description "Allow HTTP" -Access Allow -Protocol Tcp -Direction Inbound -Priority 101 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 80

$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName TestRG -Location westus -Name "NSG-FrontEnd" -SecurityRules $rule1,$rule2
```

Step:1 Create a security rule allowing access from the Internet to port 3389.
Step:2 Create a security rule allowing access from the Internet to port 80.
Step:3 Add the rules created above to a new NSG named NSG-FrontEnd.

Name                 : NSG-FrontEnd
ResourceGroupName    : rg1
Location             : westus
Id                   : /subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Microsoft.Netwo
                       rk/networkSecurityGroups/NSG-FrontEnd
Etag                 : W/"16f2b77c-1094-4bc5-91b0-07b81de13588"
ResourceGuid         : 407f5453-d8fb-4966-80fa-539215da52a2
ProvisioningState    : Succeeded
Tags                 :
SecurityRules        : \[
                         {
                           "Name": "rdp-rule",
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/securityRules/rdp-rule",
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
                         },
                         {
                           "Name": "web-rule",
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/securityRules/web-rule",
                           "Description": "Allow HTTP",
                           "Protocol": "Tcp",
                           "SourcePortRange": "*",
                           "DestinationPortRange": "80",
                           "SourceAddressPrefix": "Internet",
                           "DestinationAddressPrefix": "*",
                           "Access": "Allow",
                           "Priority": 101,
                           "Direction": "Inbound",
                           "ProvisioningState": "Succeeded"
                         }
                       \]
DefaultSecurityRules : \[
                         {
                           "Name": "AllowVnetInBound",
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/defaultSecurityRules/AllowVnetInBound",
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
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/defaultSecurityRules/AllowAzureLoadBalancerInBo
                       und",
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
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/defaultSecurityRules/DenyAllInBound",
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
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/defaultSecurityRules/AllowVnetOutBound",
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
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/defaultSecurityRules/AllowInternetOutBound",
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
                           "Etag": "W/\"16f2b77c-1094-4bc5-91b0-07b81de13588\"",
                           "Id": "/subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Micr
                       osoft.Network/networkSecurityGroups/NSG-FrontEnd/defaultSecurityRules/DenyAllOutBound",
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
Specifies the name of the network security group to create.

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

### -ResourceGroupName
Specifies the name of a resource group.
This cmdlet creates a network security group in the resource group that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the region for which to create a network security group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityRules
Specifies a list of network security rule objects to create in a network security group.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.Network.Models.PSSecurityRule]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Specifies a dictionary of tags to associate with a network security group.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
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

[Get-AzureRmNetworkSecurityGroup]()

[Remove-AzureRmNetworkSecurityGroup]()

[Set-AzureRmNetworkSecurityGroup]()

