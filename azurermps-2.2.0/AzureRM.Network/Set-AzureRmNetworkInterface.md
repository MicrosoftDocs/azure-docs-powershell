---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmNetworkInterface

## SYNOPSIS
Configures a network interface.

## SYNTAX

```
Set-AzureRmNetworkInterface -NetworkInterface <PSNetworkInterface> [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureRmNetworkInterface configures a network interface.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}



```
$nic = Get-AzureRmNetworkInterface -ResourceGroupName ResourceGroup1 -Name NetworkInterface1
$nic.IpConfigurations[0].PrivateIpAddress = "10.0.1.20"
$nic.IpConfigurations[0].PrivateIpAllocationMethod = "Static"
$nic.Tag = @{Name = "Name"; Value = "Value"}
Set-AzureRmNetworkInterface -NetworkInterface $nic
```

This example configures the network interface NetworkInterface1 in resource group ResourceGroup1 to use a static private IP address.
It also sets a tag on the network interface.

## PARAMETERS

### -NetworkInterface
Specifies the network interface to be configured.

```yaml
Type: PSNetworkInterface
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

[Get-AzureRmNetworkInterface]()

[New-AzureRmNetworkInterface]()

[Remove-AzureRmNetworkInterface]()

