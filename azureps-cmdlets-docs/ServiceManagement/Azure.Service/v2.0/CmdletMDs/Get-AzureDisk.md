---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureDisk.md
schema: 2.0.0
---

# Get-AzureDisk

## SYNOPSIS
Gets information about disks in the Azure disk repository.

## SYNTAX

```
Get-AzureDisk [[-DiskName] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureDisk** cmdlet gets information about the disks that are stored in the Azure disk repository for the current subscription.
This cmdlet returns a list of information for all disks in the repository.
To view information for a specific disk, specify the name of the disk.

## EXAMPLES

### Example 1: Get information about a disk
```
PS C:\>Get-AzureDisk -DiskName "ContosoDataDisk"
```

This command gets information data about the disk named ContosoDataDisk from the disk repository.

### Example 2: Get information about all disks
```
PS C:\>Get-AzureDisk
```

This command gets information about all the disks in the disk repository.

### Example 3: Get information about a disk
```
PS C:\>Get-AzureDisk | Where-Object {$_.AttachedTo -eq $Null } | Format-Table -AutoSize -Property "DiskName","DiskSizeInGB","MediaLink"
```

This command gets data for all of the disks in the disk repository that are not currently attached to a virtual machine.
The command gets information about all of the disks, and passes each object to the Where-Object cmdlet.
That cmdlet drops any disk that does not have a value of $Null for the **AttachedTo** property.
The command formats the list as a table by using the Format-Table cmdlet.

## PARAMETERS

### -DiskName
Specifies the name of the disk in the disk repository about which this cmdlet gets information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureDisk](.\Add-AzureDisk.md)

[Remove-AzureDisk](.\Remove-AzureDisk.md)

[Update-AzureDisk](.\Update-AzureDisk.md)

