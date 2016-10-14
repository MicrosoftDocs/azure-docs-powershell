---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureDisk.md
schema: 2.0.0
---

# Remove-AzureDisk

## SYNOPSIS
Removes a disk from the azure_2 disk repository.

## SYNTAX

```
Remove-AzureDisk [-DiskName] <String> [-DeleteVHD] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureDisk** cmdlet removes a disk from the azure_2 disk repository in the current subscription.
By default, this cmdlet does not delete the virtual hard disk (VHD) file from blob storage.
To delete the VHD, specify the *DeleteVHD* parameter.

## EXAMPLES

### Example 1: Remove a disk
```
PS C:\>Remove-AzureDisk -DiskName "ContosoDataDisk"
```

This command removes the disk named ContosoDataDisk disk from the disk repository.
The command does not delete the VHD.

### Example 2: Remove and delete a disk
```
PS C:\>Remove-AzureDisk -DiskName "ContosoDataDisk" -DeleteVHD
```

This command removes the disk named ContosoDataDisk disk from the disk repository.
This command specifies the DeleteVHD parameter.
Therefore, the command deletes the VHD from azure_2 Storage.

## PARAMETERS

### -DiskName
Specifies the name of the data disk in the disk repository that this cmdlet removes.

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

### -DeleteVHD
Indicates that this cmdlet removes the VHD from blob storage.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

## NOTES

## RELATED LINKS

[Add-AzureDisk](.\Add-AzureDisk.md)

[Get-AzureDisk](.\Get-AzureDisk.md)

[Update-AzureDisk](.\Update-AzureDisk.md)

