---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureDisk.md
schema: 2.0.0
---

# Add-AzureDisk

## SYNOPSIS
Adds a disk to the azure_2 disk repository.

## SYNTAX

```
Add-AzureDisk [-DiskName] <String> [-MediaLocation] <String> [-Label <String>] [-OS <String>]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureDisk** cmdlet adds a disk to the azure_2 disk repository in the current subscription.
This cmdlet can add a system disk or a data disk.
To add a system disk, specify an operating system type by using the *OS* parameter.

## EXAMPLES

### Example 1: Add a startup disk that uses the Windows operating system
```
PS C:\>Add-AzureDisk -DiskName "MyWinDisk" -MediaLocation "http://contosostorage.blob.core.azure.com/vhds/winserver-system.vhd" -Label "StartupDisk" -OS "Windows"
```

This command adds a system disk to your disk repository.
The system disk uses the Windows operating system.

### Example 2: Add a data disk
```
PS C:\>Add-AzureDisk -DiskName "MyDataDisk" -MediaLocation "http://yourstorageaccount.blob.core.azure.com/vhds/winserver-data.vhd" -Label "DataDisk"
```

This command adds a data disk.

### Example 3: Add a Linux system disk
```
PS C:\>Add-AzureDisk -DiskName "MyLinuxDisk" -MediaLocation "http://yourstorageaccount.blob.core.azure.com/vhds/linuxsys.vhd" -OS "Linux"
```

This command adds a Linux system disk.

## PARAMETERS

### -DiskName
Specifies the name of the disk that this cmdlet adds.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MediaLocation
Specifies the physical location of the disk in azure_2 Storage.
This value refers to a blob page in the current subscription and storage account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies a disk label for the disk that this cmdlet adds.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OS
Specifies the operating system type for a system disk.
Valid values are: 

- Windows 
- Linux 

If you do not specify this parameter, the cmdlet adds the disk as a data disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DiskContext

## NOTES

## RELATED LINKS

[Get-AzureDisk](.\Get-AzureDisk.md)

[Remove-AzureDisk](.\Remove-AzureDisk.md)

[Update-AzureDisk](.\Update-AzureDisk.md)

