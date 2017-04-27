---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmNetworkInterface

## SYNOPSIS
Gets the network interfaces in a subscription or resource group.

## SYNTAX

### NoExpandStandAloneNic (Default)
```
Get-AzureRmNetworkInterface [-Name <String>] [-ResourceGroupName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ExpandStandAloneNic
```
Get-AzureRmNetworkInterface -Name <String> -ResourceGroupName <String> -ExpandResource <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### ExpandScaleSetNic
```
Get-AzureRmNetworkInterface -Name <String> -ResourceGroupName <String> -VirtualMachineScaleSetName <String>
 -VirtualMachineIndex <String> -ExpandResource <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>]
```

### NoExpandScaleSetNic
```
Get-AzureRmNetworkInterface [-Name <String>] -ResourceGroupName <String> [-VirtualMachineScaleSetName <String>]
 [-VirtualMachineIndex <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Get-AzureRmNetworkInterface cmdlet gets the network interfaces in a subscription or resource group.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}

```
Get-AzureRmNetworkInterface
```

This example gets all network interfaces for the current subscription.

### --------------------------  Example 2  --------------------------
@{paragraph=PS C:\\\>}

```
Get-AzureRmNetworkInterface -ResourceGroupName ResourceGroup1 | Where-Object {$_.ProvisioningState -eq 'Succeeded'}
```

This example gets all network interfaces in resource group ResourceGroup1 that has a ProvisioningState of Succeeded.

## PARAMETERS

### -Name
Specifies the name of the network interface to be retrieved.

```yaml
Type: String
Parameter Sets: NoExpandStandAloneNic, NoExpandScaleSetNic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ExpandStandAloneNic, ExpandScaleSetNic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group from which network interfaces are to be retrieved.

```yaml
Type: String
Parameter Sets: NoExpandStandAloneNic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ExpandStandAloneNic, ExpandScaleSetNic, NoExpandScaleSetNic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ExpandResource
@{Text=}

```yaml
Type: String
Parameter Sets: ExpandStandAloneNic, ExpandScaleSetNic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSetName
Specifies the name of the virtual machine scale set from which network interfaces are to be retrieved.

```yaml
Type: String
Parameter Sets: ExpandScaleSetNic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: NoExpandScaleSetNic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineIndex
Specifies the virtual machine index of the virtual machine scale set from which network interfaces are to be retrieved.

```yaml
Type: String
Parameter Sets: ExpandScaleSetNic
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: NoExpandScaleSetNic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[New-AzureRmNetworkInterface]()

[Remove-AzureRmNetworkInterface]()

[Set-AzureRmNetworkInterface]()

