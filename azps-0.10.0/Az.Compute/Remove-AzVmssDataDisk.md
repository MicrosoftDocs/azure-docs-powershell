---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
online version: https://learn.microsoft.com/en-us/powershell/module/az.compute/remove-azvmssdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Remove-AzVmssDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Remove-AzVmssDataDisk.md
---

# Remove-AzVmssDataDisk

## SYNOPSIS
Removes a data disk from the VMSS.

## SYNTAX

### NameParameterSet
```
Remove-AzVmssDataDisk [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LunParameterSet
```
Remove-AzVmssDataDisk [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [-Lun] <Int32>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzVmssDataDisk** cmdlet removes a data disk from the Virtual Machine Scale Set (VMSS) instance.

## EXAMPLES

### Example 1
```
PS C:\> Remove-AzVmssDataDisk -VirtualMachineScaleSet $vmss -Name 'DataDisk1'
```

This command removes the data disk named 'DataDisk1' from the VMSS object.

### Example 2
```
PS C:\> Remove-AzVmssDataDisk -VirtualMachineScaleSet $vmss -Lun 0
```

This command removes the data disk of LUN 0 from the VMSS object.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lun
Specifies the logical unit number of the disk.

```yaml
Type: Int32
Parameter Sets: LunParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the disk.

```yaml
Type: String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Specify the VMSS object.

```yaml
Type: PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSet
System.String
System.Nullable`1[[System.Int32, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Management.Compute.Models.VirtualMachineScaleSet

## NOTES

## RELATED LINKS

