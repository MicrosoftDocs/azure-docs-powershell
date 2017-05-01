---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmNetworkSecurityGroup

## SYNOPSIS
Gets a network security group.

## SYNTAX

### NoExpand
```
Get-AzureRmNetworkSecurityGroup [-Name <String>] [-ResourceGroupName <String>] [<CommonParameters>]
```

### Expand
```
Get-AzureRmNetworkSecurityGroup -Name <String> -ResourceGroupName <String> -ExpandResource <String>
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureRmNetworkSecurityGroup cmdlet gets an Azure network security group.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}





```
Get-AzureRmNetworkSecurityGroup -Name  nsg1 -ResourceGroupName "rg1"
```

Returns contents of Azure network security group "nsg1" in resource group "rg1"

Name                 : nsg1
ResourceGroupName    : rg1
Location             : westus
Id                   : /subscriptions/\<subscriptionId\>/resourceGroups/rg1/providers/Microsoft.Netwo
                       rk/networkSecurityGroups/nsg1
Etag                 : W/"b4833539-3f97-4c90-ab00-8521d7f5ca35"
ResourceGuid         : 91e36ce0-8640-41db-a2b9-20e8a17e167c
ProvisioningState    : Succeeded
Tags                 :
SecurityRules        : \[\]
DefaultSecurityRules : \[
                         {
                           "Name": "AllowVnetInBound",
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
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
                           "Etag": "W/\"b4833539-3f97-4c90-ab00-8521d7f5ca35\"",
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
Specifies the name of the network security group to get.

```yaml
Type: String
Parameter Sets: NoExpand
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Expand
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the network security group to get.

```yaml
Type: String
Parameter Sets: NoExpand
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Expand
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExpandResource
@{Text=}

```yaml
Type: String
Parameter Sets: Expand
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[New-AzureRmNetworkSecurityGroup]()

[Remove-AzureRmNetworkSecurityGroup]()

[Set-AzureRmNetworkSecurityGroup]()

