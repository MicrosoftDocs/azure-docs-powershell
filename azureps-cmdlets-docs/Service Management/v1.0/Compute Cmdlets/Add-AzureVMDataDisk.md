---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Add-AzureVMDataDisk
## SYNOPSIS
Add Data Disk to VM

## SYNTAX

```
Add-AzureVMDataDisk [-VM] <PSVirtualMachine> [-Name] <String> [[-VhdUri] <String>] [-Caching]
 [-DiskSizeInGB] <Int32> [[-Lun] <Int32>] [-Profile <AzureProfile>]
```

## DESCRIPTION
This cmdlets allows you to add a Data Disk to the VM at creation time or to an existing VM

## EXAMPLES

### --------------------------  Add Data Disk to a new VM  --------------------------
```
PS C:\> # Create the local VM Object
          $vm =  New-AzureVMConfig ?VMName ?myVM? ?VMSize ?Standard_A1" -AvailabilitySetID $as1.Id

          # Add Data Disk disk1 to this VM
          Add-AzureVMDataDisk ?VM $vm ?Name "disk1" ?VhdUri "http://storageaccountname.blob.core.windows.net/vhds/test2.vhd" ?LUN 0 ?Caching ReadOnly ?DiskSizeinGB 1
```

### --------------------------  Add a Data Disk to an existing VM  --------------------------
```
PS C:\> # Get the VM
          $vm = Get-AzureVM -ResourceGroupName "myRG" -Name "crpVM"

          # Add Data Disk disk1 to VM
          Add-AzureVMDataDisk ?VM $vm ?Name "disk1" ?VhdUri "http://storageaccountname.blob.core.windows.net/vhds/test2.vhd" ?LUN 0 ?Caching ReadOnly ?DiskSizeinGB 1

          # Update VM state
          Update-AzureVM -ResourceGroupName "myRG" -Name "crpVM" ?VM $vm
```

## PARAMETERS

### -Caching
Specifies the caching mode of the disk.
This setting impacts the consistency and performance of the disk.
Note: Changing this value causes the Virtual Machine to reboot.
            Possible values are:
            ?
ReadOnly
            ?
ReadWrite
          The default value is ReadWrite.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: ReadOnly, ReadWrite

Required: False
Position: 4
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -DiskSizeInGB
Specifies the size, in GB, of an empty disk to be attached to the Virtual Machine.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Lun
Specifies the Logical Unit Number (LUN) for the data disk.
If the disk is the first disk that is added, this element is optional and the default value of 0 is used.
If more than one disk is being added, this element is required.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Name
Name of the Data Disk

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Profile
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

### -VhdUri
Specifies the VHD file that needs to be created when a platform image or user image is used.
This is where the image blob will be copied to start the VM from.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -VM
Local VM Object to add the Data Disk to.
The local VM object can be created with New-AzureVMConfig cmdlet or gotten through the Get-AzureVM cmdlet.

```yaml
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

