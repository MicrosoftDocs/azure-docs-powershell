---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmVirtualNetwork

## SYNOPSIS
Gets a virtual network in a resource group.

## SYNTAX

### NoExpand
```
Get-AzureRmVirtualNetwork [-Name <String>] [-ResourceGroupName <String>] [<CommonParameters>]
```

### Expand
```
Get-AzureRmVirtualNetwork -Name <String> -ResourceGroupName <String> -ExpandResource <String>
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureRmVirtualNetwork cmdlet gets one or more virtual networks in a resource group.

## EXAMPLES

### --------------------------  Example 1: Get a virtual network  --------------------------
@{paragraph=PS C:\\\>}





```
Get-AzureRmVirtualNetwork -Name MyVirtualNetwork -ResourceGroupName TestResourceGroup
```

Gets the virtual network named MyVirtualNetwork in the resource group TestResourceGroup.

Name              : MyVirtualNetwork
ResourceGroupName : TestResourceGroup
Location          : centralus
Id                : /subscriptions/bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb/resourceGroups/TestResourceGroup/providers/Microsoft.Network/virtualNetworks/MyVirtualNetwork
Etag              : W/"0bc06317-a23c-4044-8336-123ba68bb99d"
ResourceGuid      : aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa
ProvisioningState : Succeeded
Tags              :
AddressSpace      : {
                      "AddressPrefixes": \[
                        "10.0.0.0/16"
                      \]
                    }
DhcpOptions       : {
                      "DnsServers": \[\]
                    }
Subnets           : \[
                      {
                        "Name": "frontendSubnet",
                        "Etag": "W/\"0bc06317-a23c-4044-8336-123ba68bb99d\"",
                        "Id": "/subscriptions/bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb/resourceGroups/TestResourceGroup/providers/Microsoft.Network/virtualNetworks/MyVirtualNetwork/subnets/frontendSubnet",
                        "AddressPrefix": "10.0.1.0/24",
                        "IpConfigurations": \[\],
                        "ProvisioningState": "Succeeded"
                      },
                      {
                        "Name": "backendSubnet",
                        "Etag": "W/\"0bc06317-a23c-4044-8336-123ba68bb99d\"",
                        "Id": "/subscriptions/bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb/resourceGroups/TestResourceGroup/providers/Microsoft.Network/virtualNetworks/MyVirtualNetwork/subnets/backendSubnet",
                        "AddressPrefix": "10.0.2.0/24",
                        "IpConfigurations": \[\],
                        "ProvisioningState": "Succeeded"
                      }
                    \]

## PARAMETERS

### -Name
Specifies the name of the virtual network to get.

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
Specifies the name of the resource group that contains the virtual network.

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

[New-AzureRmVirtualNetwork]()

[Remove-AzureRmVirtualNetwork]()

[Set-AzureRmVirtualNetwork]()

