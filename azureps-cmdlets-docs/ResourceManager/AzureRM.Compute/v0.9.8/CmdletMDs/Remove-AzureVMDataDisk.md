---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Add-AzureVMDataDisk.md
schema: 2.0.0
---

# Remove-AzureVMDataDisk

## SYNOPSIS
Removes a data disk from a virtual machine.

## SYNTAX

```
Remove-AzureVMDataDisk [-VM] <PSVirtualMachine> -DataDiskNames <String[]> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureVMDataDisk** cmdlet removes a data disk from a virtual machine.

## EXAMPLES

### Example 1: Remove a data disk from a virtual machine
```
PS C:\>$VirtualMachine = Get-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" 
PS C:\> Remove-AzureVMDataDisk -VM $VirtualMachine -Name "disk3" 
PS C:\> Update-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -VM $VirtualMachine
```

The first command gets the virtual machine named VirtualMachine07 by using the **Get-AzureVM** cmdlet.
The command stores the virtual machine in the $VirtualMachine variable.

The second command removes the data disk named disk3 from the virtual machine stored in $VirtualMachine.

The final command updates the state of the virtual machine stored in $VirtualMachine in ResourceGroup11.

## PARAMETERS

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the local virtual machine object from which to remove a data disk.
To obtain a virtual machine object, use the **Get-AzureVM** cmdlet.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DataDiskNames
The virtual machine data disk's name.```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Name

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

## RELATED LINKS

[Add-AzureVMDataDisk](.\Add-AzureVMDataDisk.md)

[Get-AzureVM](.\Get-AzureVM.md)

