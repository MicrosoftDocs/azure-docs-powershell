---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Remove-AzureVMDataDisk.md
schema: 2.0.0
---

# Add-AzureVMDataDisk

## SYNOPSIS
Adds a data disk to a virtual machine.

## SYNTAX

```
Add-AzureVMDataDisk [-VM] <PSVirtualMachine> [-Name] <String> [[-VhdUri] <String>] [[-Caching] <String>]
 [-DiskSizeInGB] <Int32> [[-Lun] <Int32>] [-CreateOption] <String> [[-SourceImageUri] <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureVMDataDisk** cmdlet adds a data disk to a virtual machine.
You can add a data disk when you create a virtual machine, or you can add a data disk to an existing virtual machine.

## EXAMPLES

### Example 1: Add data disks to a new virtual machine
```
PS C:\>$VirtualMachine = New-AzureVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" 
PS C:\> $DataDiskVhdUri01 = "https://contoso.blob.core.windows.net/test/data1.vhd"
PS C:\> $DataDiskVhdUri02 = "https://contoso.blob.core.windows.net/test/data2.vhd"
PS C:\> $DataDiskVhdUri03 = "https://contoso.blob.core.windows.net/test/data3.vhd"
PS C:\> $VirtualMachine = Add-AzureVMDataDisk -VM $VirtualMachine -Name 'DataDisk1' -Caching 'ReadOnly' -DiskSizeInGB 10 -Lun 0 -VhdUri $DataDiskVhdUri1 -CreateOption Empty
PS C:\> $VirtualMachine = Add-AzureVMDataDisk -VM $VirtualMachine -Name 'DataDisk2' -Caching 'ReadOnly' -DiskSizeInGB 11 -Lun 1 -VhdUri $DataDiskVhdUri2 -CreateOption Empty
PS C:\> $VirtualMachine = Add-AzureVMDataDisk -VM $VirtualMachine -Name 'DataDisk3' -Caching 'ReadOnly' -DiskSizeInGB 12 -Lun 2 -VhdUri $DataDiskVhdUri3 -CreateOption Empty
```

The first command creates a virtual machine object, and then stores it in the $VirtualMachine variable.
The command assigns a name and size to the virtual machine.

The next three commands assign paths of three data disks to the $DataDiskVhdUri01, $DataDiskVhdUri02, and $DataDiskVhdUri03 variables.
This approach is only for readability of the following commands.

The final three commands each adds a data disk to the virtual machine stored in $VirtualMachine.
The command specifies the name and location for the disk, and other properties of the disk.
The URI of each disk is stored in $DataDiskVhdUri01, $DataDiskVhdUri02, and $DataDiskVhdUri03.

### Example 2: Add a data disk to an existing virtual machine
```
PS C:\>$VirtualMachine = Get-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
PS C:\> Add-AzureVMDataDisk -VM $VirtualMachine -Name "disk1" -VhdUri "https://contoso.blob.core.windows.net/vhds/diskstandard03.vhd" -LUN 0 -Caching ReadOnly -DiskSizeinGB 1 -CreateOption Empty
PS C:\> Update-AzureVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07" -VM $VirtualMachine
```

The first command gets the virtual machine named VirtualMachine07 by using the **Get-AzureVM** cmdlet.
The command stores the virtual machine in the $VirtualMachine variable.

The second command adds a data disk to the virtual machine stored in $VirtualMachine.

The final command updates the state of the virtual machine stored in $VirtualMachine in ResourceGroup11.

## PARAMETERS

### -Caching
Specifies the caching mode of the disk.
Valid values are:

- ReadOnly
- ReadWrite

The default value is ReadWrite.
Changing this value causes the virtual machine to restart.

This setting affects the consistency and performance of the disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: ReadOnly, ReadWrite

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CreateOption
Specifies whether this cmldet creates a disk in the virtual machine from a platform or user image, creates an empty disk, or attaches an existing disk.
Valid values are: 

- Attach 
- Empty 
- FromImage

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: empty, attach, fromImage

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskSizeInGB
Specifies the size, in gigabytes, of an empty disk to attach to a virtual machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lun
Specifies the logical unit number (LUN) for a data disk.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the data disk to add.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -SourceImageUri
Specifies the source URI of the disk that this cmdlet attaches.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SourceImage

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VhdUri
Specifies the Uniform Resource Identifier (URI) for the virtual hard disk (VHD) file to create when a platform image or user image is used.
This cmdlet copies the image binary large object (BLOB) to this location.
This is the location from which to start the virtual machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the local virtual machine object to which to add a data disk.
To obtain a virtual machine object, use the **Get-AzureVM** cmdlet.
Create a virtual machine object by using the **New-AzureVMConfig** cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzureVMDataDisk](.\Remove-AzureVMDataDisk.md)

[Get-AzureVM](.\Get-AzureVM.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

