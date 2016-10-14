---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureRmVM.md
schema: 2.0.0
---

# Update-AzureRmVM

## SYNOPSIS
Updates the state of an azure_2 virtual machine.

## SYNTAX

### ResourceGroupNameParameterSetName (Default)
```
Update-AzureRmVM -VM <PSVirtualMachine> [-Tags <Hashtable[]>] [-ResourceGroupName] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IdParameterSetName
```
Update-AzureRmVM -VM <PSVirtualMachine> [-Tags <Hashtable[]>] [-Id] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzureRmVM** cmdlet updates the state of an azure_2 virtual machine to the state of a virtual machine object.

## EXAMPLES

### Example 1: Update a virtual machine
```
PS C:\>Update-AzureRmVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -VM $VirtualMachine
```

This command updates the virtual machine named VirtualMachine07 in ResourceGroup11.
The command updates it by using another virtual machine object, stored in the $VirtualMachine variable.
To obtain a virtual machine object, use the **Get-AzureRmVM** cmdlet.

## PARAMETERS

### -VM
Specifies a local virtual machine object.
To obtain a virtual machine object, use the Get-AzureRmVM cmdlet.
This virtual machine object contains the updated state for the virtual machine.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tags
Specifies the resources and resource groups can be tagged with a set of name-value pairs.
Adding tags to resources enables you to group resources together across resource groups and to create your own views.
Each resource or resource group can have a maximum of 15 tags.

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

### -ResourceGroupName
Specifies the name of the resource group of the virtual machine.

```yaml
Type: String
Parameter Sets: ResourceGroupNameParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
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
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the Resource ID of the virtual machine.

```yaml
Type: String
Parameter Sets: IdParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
psdx_whatifdesc

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmVM](.\Get-AzureRmVM.md)

[New-AzureRmVM](.\New-AzureRmVM.md)

[Remove-AzureRmVM](.\Remove-AzureRmVM.md)

[Restart-AzureRmVM](.\Restart-AzureRmVM.md)

[Start-AzureRmVM](.\Start-AzureRmVM.md)

[Stop-AzureRmVM](.\Stop-AzureRmVM.md)

[New-AzureRmVMConfig](.\New-AzureRmVMConfig.md)

