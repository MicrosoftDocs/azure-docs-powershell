---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmNetworkSecurityGroup

## SYNOPSIS
Sets the goal state for a network security group.

## SYNTAX

```
Set-AzureRmNetworkSecurityGroup -NetworkSecurityGroup <PSNetworkSecurityGroup> [<CommonParameters>]
```

## DESCRIPTION
The Set-AzureRmNetworkSecurityGroup cmdlet sets the goal state for an Azure network security group.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmNetworkSecurityGroup -Name  nsg1 -ResourceGroupName rg1 | Add-AzureRmNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389 | Set-AzureRmNetworkSecurityGroup
```

Retrieves an Azure network security group named "nsg1" from resource group "rg1" using 'Get-AzureRmNetworkSecurityGroup'.
Adds a network security rule named "rdp-rule" that allows traffic from internet on port 3389 to the retrieved network security group object using 'Add-AzureRmNetworkSecurityRuleConfig'.
Persists the modified Azure network security group using 'Set-AzureRmNetworkSecurityGroup'.

## PARAMETERS

### -NetworkSecurityGroup
A Network Security Group object representing the goal state to which the Network Security Group should be set.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Get-AzureRmNetworkSecurityGroup]()

[New-AzureRmNetworkSecurityGroup]()

[Remove-AzureRmNetworkSecurityGroup]()

