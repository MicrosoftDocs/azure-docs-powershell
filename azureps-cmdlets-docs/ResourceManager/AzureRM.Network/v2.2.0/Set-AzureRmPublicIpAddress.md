---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmPublicIpAddress

## SYNOPSIS
Updates a public IP address resource corresponding to the specified object.

## SYNTAX

```
Set-AzureRmPublicIpAddress -PublicIpAddress <PSPublicIpAddress> [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureRmPublicIpAddress cmdlet updates the public IP address resource corresponding to the object specified with -PublicIpAddress parameter.
Refer to New-AzureRmPublicIpAddress detailed help for possible parameters that can be changed on a public IP address object.

## EXAMPLES

### --------------------------  1: Change allocation method of a public IP address  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
PS C:\> $publicIp.PublicIpAllocationMethod = "Dynamic"

PS C:\> Set-AzureRmPublicIpAddress -PublicIpAddress $publicIp
PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

First command gets the public IP address resource with name $publicIPName in the resource group $rgName.
Second command sets the allocation method of the public IP address object to "Static".
Set-AzureRmPublicIPAddress command updates the public IP address resource with the updated object, and modifies the allocation method to 'Static'.
A public IP address gets allocated immediately.

--- $publicIp before change  ---
Name                     : mypublicip
ResourceGroupName        : arm-test
Location                 : centralus
Id                       : /subscriptions/.../resourceGroups/arm-test/providers/Microsoft.Network/publicIPAddresses/mypublicip
Etag                     : W/"..."
ResourceGuid             : 3158adf7-21e3-4c88-afab-b7953bf02c9d
ProvisioningState        : Succeeded
Tags                     :
PublicIpAllocationMethod : Dynamic
IpAddress                : Not Assigned
IdleTimeoutInMinutes     : 4
IpConfiguration          : null
DnsSettings              : {
                             "DomainNameLabel": "mypublicipdnslabel",
                             "Fqdn": "mypublicipdnslabel.centralus.cloudapp.azure.com"
                           }

--- $publicIp after change ---
Name                     : mypublicip
ResourceGroupName        : arm-test
Location                 : centralus
Id                       : /subscriptions/.../resourceGroups/arm-test/providers/Microsoft.Network/publicIPAddresses/mypublicip
Etag                     : W/"eed851a7-8b77-4310-aac2-87d0139616a8"
ResourceGuid             : 3158adf7-21e3-4c88-afab-b7953bf02c9d
ProvisioningState        : Succeeded
Tags                     :
PublicIpAllocationMethod : Static
IpAddress                : 13.89.55.182
IdleTimeoutInMinutes     : 4
IpConfiguration          : null
DnsSettings              : {
                             "DomainNameLabel": "mypublicipdnslabel",
                             "Fqdn": "mypublicipdnslabel.centralus.cloudapp.azure.com"
                           }

### --------------------------  2: Change DNS domain label of a public IP address  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
PS C:\> $publicIp.DnsSettings.DomainNameLabel = "newdnsprefix"

PS C:\> Set-AzureRmPublicIpAddress -PublicIpAddress $publicIp
PS C:\> $publicIp = Get-AzureRmPublicIpAddress -Name $publicIpName -ResourceGroupName $rgName
```

First command gets the public IP address resource with name $publicIPName in the resource group $rgName.
Second command sets the DomainNameLabel property to the required dns prefix.
Set-AzureRmPublicIPAddress command updates the public IP address resource with the updated object.
DomainNameLabel & Fqdn are modified as expected.

--- $publicIp before change  ---
Name                     : mypublicip
ResourceGroupName        : arm-test
Location                 : centralus
Id                       : /subscriptions/.../resourceGroups/arm-test/providers/Microsoft.Network/publicIPAddresses/mypublicip
Etag                     : W/"..."
ResourceGuid             : 3158adf7-21e3-4c88-afab-b7953bf02c9d
ProvisioningState        : Succeeded
Tags                     :
PublicIpAllocationMethod : Dynamic
IpAddress                : Not Assigned
IdleTimeoutInMinutes     : 4
IpConfiguration          : null
DnsSettings              : {
                             "DomainNameLabel": "mypublicipdnslabel",
                             "Fqdn": "mypublicipdnslabel.centralus.cloudapp.azure.com"
                           }

--- $publicIp after change ---
Name                     : mypublicip
ResourceGroupName        : arm-test
Location                 : centralus
Id                       : /subscriptions/.../resourceGroups/arm-test/providers/Microsoft.Network/publicIPAddresses/mypublicip
Etag                     : W/"..."
ResourceGuid             : 3158adf7-21e3-4c88-afab-b7953bf02c9d
ProvisioningState        : Succeeded
Tags                     :
PublicIpAllocationMethod : Dynamic
IpAddress                : Not Assigned
IdleTimeoutInMinutes     : 4
IpConfiguration          : null
DnsSettings              : {
                             "DomainNameLabel": "newdnsprefix",
                             "Fqdn": "newdnsprefix.centralus.cloudapp.azure.com"
                           }

## PARAMETERS

### -PublicIpAddress
Specifies a PublicIpAddress object that represents the goal state to which the public IP address should be set.

```yaml
Type: PSPublicIpAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmPublicIpAddress]()

[New-AzureRmPublicIpAddress]()

[Remove-AzureRmPublicIpAddress]()

