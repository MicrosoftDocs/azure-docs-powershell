---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
online version: .\Get-AzureVM.md
schema: 2.0.0
---

# Set-AzureVMOSDisk

## SYNOPSIS
Sets the operating system disk properties on a virtual machine.

## SYNTAX

### WindowsParamSet (Default)
```
Set-AzureVMOSDisk [-VM] <PSVirtualMachine> [-Name] <String> [[-VhdUri] <String>] [[-Caching] <String>]
 [[-SourceImageUri] <String>] [-CreateOption] <String> [-Windows] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### LinuxParamSet
```
Set-AzureVMOSDisk [-VM] <PSVirtualMachine> [-Name] <String> [[-VhdUri] <String>] [[-Caching] <String>]
 [[-SourceImageUri] <String>] [-CreateOption] <String> [-Linux] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMOSDisk** cmdlet set the operating system disk properties on a virtual machine.

## EXAMPLES

### Example 1: Sets properties on a virtual machine
```
PS C:\>$AvailabilitySet = Get-AzureAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03" 
PS C:\> $VirtualMachine = New-AzureVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> Set-AzureVMOSDisk -VM $VirtualMachine -Name "OsDisk02" -VhdUri "os.vhd" -Caching ReadWrite
```

The first command gets the availability set named AvailablitySet03 in the resource group named ResourceGroup11, and then stores that object in the $AvailabilitySet variable.

The second command creates a virtual machine object, and then stores it in the $VirtualMachine variable.
The command assigns a name and size to the virtual machine.
The virtual machine belongs to the availability set stored in $AvailabilitySet.

The final command sets the properties on the virtual machine in $VirtualMachine.

## PARAMETERS

### -Caching
Specifies the caching mode of the operating system disk.
Valid values are: 

- ReadOnly
- ReadWrite

The default value is ReadWrite.
Changing the caching value causes the virtual machine to restart.

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

This setting affects the consistency and performance of the disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: empty, attach, fromImage

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Linux
Indicates that the operating system on the user image is Linux.
Specify this parameter for user image based virtual machine deployment.

```yaml
Type: SwitchParameter
Parameter Sets: LinuxParamSet
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the operating system disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OSDiskName, DiskName

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
This setting affects the consistency and performance of the disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SourceImage

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VhdUri
Specifies the Uniform Resource Identifier (URI) of a virtual hard disk (VHD).

For an image based virtual machine, this parameter specifies the VHD file to create when a platform image or user image is specified.
This is the location from which the image binary large object (BLOB) is copied to start the virtual machine.

For a disk based virtual machine boot scenario, this parameter specifies the VHD file that the virtual machine uses directly for starting up.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OSDiskVhdUri, DiskVhdUri

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the local virtual machine object on which to set operating system disk properties.
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

### -Windows
Indicates that the operating system on the user image is Windows.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsParamSet
Aliases: 

Required: False
Position: 7
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

[Get-AzureVM](.\Get-AzureVM.md)

[Get-AzureAvailabilitySet](.\Get-AzureAvailabilitySet.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

