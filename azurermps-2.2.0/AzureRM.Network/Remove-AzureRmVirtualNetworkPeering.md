---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-AzureRmVirtualNetworkPeering

## SYNOPSIS
Deletes a Virtual network Peering that has been previously created

## SYNTAX

```
Remove-AzureRmVirtualNetworkPeering -VirtualNetworkName <String> -Name <String> -ResourceGroupName <String>
 [-Force] [-PassThru] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
This cmdlet deletes an existing virtual network peering.
Note that a peering must exist before one can remove or delete it.
Deleting a peering between two virtual networks means that virtual machines in these virtual networks can no longer communicate via private IP addresses, that is, through virtual network peering.

## EXAMPLES

### --------------------------  Example 1 Delete a Virtual Network Peering  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\> Remove-AzureRmVirtualNetworkPeering -Name "LinkToVNet2" -VirtualNetworkName "MyVirtualNetwork" -ResourceGroupName "MyResourceGroup"
```

This command deletes a previously created Virtual Network Peering called "LinkToVNet2" located in "MyVirtualNetwork" within the resource group called "MyResourceGroup"

## PARAMETERS

### -VirtualNetworkName
The virtual network name.

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

### -Name
The virtual network peering name.

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

### -ResourceGroupName
The resource group name

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

### -Force
@{Text=}

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

### -PassThru
@{Text=}

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

### -WhatIf
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking, peering

## RELATED LINKS

[Get-AzureRmVirtualNetworkPeering]()

[Set-AzureRmVirtualNetworkPeering]()

[Add-AzureRmVirtualNetworkPeering]()

