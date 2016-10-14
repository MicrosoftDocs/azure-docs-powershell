---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureDataDisk.md
schema: 2.0.0
---

# Add-AzureDataDisk

## SYNOPSIS
Adds a data disk to a virtual machine.

## SYNTAX

### CreateNew (Default)
```
Add-AzureDataDisk [-CreateNew] [-DiskSizeInGB] <Int32> [-DiskLabel] <String> [-LUN] <Int32>
 [-MediaLocation <String>] [-HostCaching <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Import
```
Add-AzureDataDisk [-Import] [-DiskName] <String> [-LUN] <Int32> [-HostCaching <String>] -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### ImportFrom
```
Add-AzureDataDisk [-ImportFrom] [-DiskLabel] <String> [-LUN] <Int32> -MediaLocation <String>
 [-HostCaching <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureDataDisk** cmdlet adds a new or existing data disk to an Azure virtual machine object.
Use the *CreateNew* parameter to create a new data disk that has a specified size and label.
Use the *Import* parameter to attach an existing disk from the image repository.
Use the *ImportFrom* parameter to attach an existing disk from a blob in a storage account.
You can specify the host-cache mode of the attached data disk.

## EXAMPLES

### Example 1: Import a data disk from the repository
```
PS C:\>Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Add-AzureDataDisk -Import -DiskName "Disk68" -LUN 0 | Update-AzureVM
```

This command gets a virtual machine object for the virtual machine named VirtualMachine07 in the ContosoService cloud service by using the Get-AzureVM cmdlet.
The command passes it to the current cmdlet by using the pipeline operator.
That command attaches an existing data disk from the repository to the virtual machine.
The data disk has a LUN of 0.
The command updates the virtual machine to reflect your changes by using the Update-AzureVM cmdlet.

### Example 2: Add a new data disk
```
PS C:\>Get-AzureVM "ContosoService" -Name "VirtualMachine08" | Add-AzureDataDisk -CreateNew -DiskSizeInGB 128 -DiskLabel "main" -LUN 0 | Update-AzureVM
```

This command gets a virtual machine object for the virtual machine named VirtualMachine08.
The command passes it to the current cmdlet.
That command attaches a new data disk named MyNewDisk.vhd.
The cmdlet creates the disk in the vhds container in the default storage account of the current subscription.
The command updates the virtual machine to reflect your changes.

### Example 3: Add a data disk from a specified location
```
PS C:\>Get-AzureVM "ContosoService" -Name "Database" | Add-AzureDataDisk -ImportFrom -MediaLocation "https://contosostorage.blob.core.windows.net/container07/Disk14.vhd" -DiskLabel "main" -LUN 0 | Update-AzureVM
```

This command gets a virtual machine object for the virtual machine named Database.
The command passes it to the current cmdlet.
That command attaches an existing data disk named Disk14.vhd from the specified location.
The command updates the virtual machine to reflect your changes.

## PARAMETERS

### -CreateNew
Indicates that this cmdlet creates a data disk.

```yaml
Type: SwitchParameter
Parameter Sets: CreateNew
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSizeInGB
Specifies the logical disk size, in gigabytes, for a new data disk.

```yaml
Type: Int32
Parameter Sets: CreateNew
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskLabel
Specifies the disk label for a new data disk.

```yaml
Type: String
Parameter Sets: CreateNew, ImportFrom
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LUN
Specifies the logical unit number (LUN) for the data drive in the virtual machine.
Valid values are: 0 through 15.
Each data disk must have a unique LUN.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaLocation
Specifies the location of the blob in an Azure storage account where this cmdlet stores the data disk.
If you do not specify a location, the cmdlet stores the data disk in the vhds container in the default storage account for the current subscription.
If a vhds container does not exist, the cmdlet creates a vhds container.

```yaml
Type: String
Parameter Sets: CreateNew
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ImportFrom
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostCaching
Specifies the host level caching settings of the disk.
Valid values are: 

- None 
- ReadOnly 
- ReadWrite

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine object to which this cmdlet attaches a data disk.
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

### -Import
Indicates that this cmdlet imports an existing data disk from the image repository.

```yaml
Type: SwitchParameter
Parameter Sets: Import
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskName
Specifies the name of a data disk in the disk repository.

```yaml
Type: String
Parameter Sets: Import
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImportFrom
Indicates that this cmdlet imports an existing data disk from a blob in a storage account.

```yaml
Type: SwitchParameter
Parameter Sets: ImportFrom
Aliases: 

Required: True
Position: 0
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

[Get-AzureDataDisk](.\Get-AzureDataDisk.md)

[Get-AzureVM](.\Get-AzureVM.md)

[Remove-AzureDataDisk](.\Remove-AzureDataDisk.md)

[Set-AzureDataDisk](.\Set-AzureDataDisk.md)

[Update-AzureVM](.\Update-AzureVM.md)

