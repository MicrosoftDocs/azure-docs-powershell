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
Set-AzureRmNetworkInterface -NetworkInterface <PSNetworkInterface> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
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

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmNetworkInterface]()

[New-AzureRmNetworkInterface]()

[Remove-AzureRmNetworkInterface]()

