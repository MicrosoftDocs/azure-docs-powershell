---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureDataDisk.md
schema: 2.0.0
---

# Set-AzureDataDisk

## SYNOPSIS
Modifies the host caching of an existing data disk on an Azure virtual machine.

## SYNTAX

### NoResize
```
Set-AzureDataDisk [-HostCaching] <String> [-LUN] <Int32> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Resize
```
Set-AzureDataDisk [-DiskName] <String> [-ResizedSizeInGB] <Int32> -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureDataDisk** cmdlet modifies the cache attributes of an existing data disk on an Azure virtual machine.
Specify which data disk to update by its logical unit number (LUN).

## EXAMPLES

### Example 1: Modify the host caching for a data disk
```
PS C:\>Get-AzureVM "ContosoService" | Set-AzureDataDisk -VM "VirtualMachine07" -LUN 2 -HostCaching ReadOnly | Update-AzureVM
```

This command gets the virtual machines that run on the service named ContosoService by using the Get-AzureVM cmdlet.
The command passes them to the current cmdlet by using the pipeline operator.
That cmdlet sets the data disk at LUN 2 of the virtual machine named VirtualMachine07 to use ReadOnly host caching.
The command updates the virtual machine to reflect your changes by using the Update-AzureVM cmdlet.

### Example 2: Modify the host caching for all data disks on a virtual machine
```
PS C:\>Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Get-AzureDataDisk | Set-AzureDataDisk -HostCaching ReadWrite | Update-AzureVM
```

This command gets an object for the virtual machine named VirtualMachine07 on the ContosoService cloud service.
The command passes it to the Get-AzureDataDisk cmdlet, which gets the data disks for that virtual machine.
The current cmdlet then sets the host caching mode of each data disks to ReadWrite.
The command updates the virtual machine to reflect your changes.

## PARAMETERS

### -HostCaching
Specifies the host level caching settings of the disk.
Valid values are: 

- None 
- ReadOnly 
- ReadWrite

```yaml
Type: String
Parameter Sets: NoResize
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LUN
Specifies the LUN for the data drive in the virtual machine.
Valid values are: 0 through 15.

```yaml
Type: Int32
Parameter Sets: NoResize
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine object that is attached to the data disk.
To obtain a virtual machine object, use the Get-AzureVM cmdlet.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -DiskName
Specifies the name of the data disk configuration that this cmdlet modifies.

```yaml
Type: String
Parameter Sets: Resize
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResizedSizeInGB
Specifies the new size, in gigabytes, for the data disk.
The new size must be larger than the current size.

```yaml
Type: Int32
Parameter Sets: Resize
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureDataDisk](.\Add-AzureDataDisk.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Get-AzureDataDisk](.\Get-AzureDataDisk.md)

[Remove-AzureDataDisk](.\Remove-AzureDataDisk.md)

[Update-AzureVM](.\Update-AzureVM.md)

