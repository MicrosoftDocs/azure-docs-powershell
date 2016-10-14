---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleDeviceBackupScheduleAddConfig.md
schema: 2.0.0
---

# New-AzureStorSimpleDeviceBackupScheduleUpdateConfig

## SYNOPSIS
Creates a backup schedule update configuration object.

## SYNTAX

```
New-AzureStorSimpleDeviceBackupScheduleUpdateConfig [-Id] <String> [-BackupType] <String>
 [-RecurrenceType] <String> [-RecurrenceValue] <Int32> [-RetentionCount] <Int64>
 [[-StartFromDateTime] <String>] [[-Enabled] <Boolean>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleDeviceBackupScheduleUpdateConfig** cmdlet creates a **BackupScheduleUpdateRequest** configuration object.
Use this configuration object to update a backup policy by using the **Set-AzureStorSimpleDeviceBackupPolicy** cmdlet.

## EXAMPLES

### Example 1: Create a schedule update request
```
PS C:\>New-AzureStorSimpleDeviceBackupScheduleUpdateConfig -Id "147f734d-a31a-4473-8501-6ba38be2cb30" -BackupType CloudSnapshot -RecurrenceType Hourly -RecurrenceValue 1 -RetentionCount 50 -Enabled $True
VERBOSE: ClientRequestId: ef346641-54b4-4273-8898-7f863e7c5b7e_PS


BackupType     : CloudSnapshot
Id             : 147f734d-a31a-4473-8501-6ba38be2cb30
Recurrence     : Microsoft.WindowsAzure.Management.StorSimple.Models.ScheduleRecurrence
RetentionCount : 50
StartTime      : 2014-12-16T00:39:32+05:30
Status         : Enabled
```

This command creates a backup schedule update request for the schedule that has the specified ID.
The request is to make the schedule a cloud snapshot backup that recurs every hour.
The backups are kept for 50 days.
This schedule is enabled from the default time, which is the current time.

## PARAMETERS

### -BackupType
Specifies the backup type.
Valid values are: LocalSnapshot and CloudSnapshot.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: LocalSnapshot, CloudSnapshot

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Indicates whether to enable the backup schedule.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the instance ID of the backup schedule to update.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

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

### -RecurrenceType
Specifies the type of recurrence for this backup schedule.
Valid values are: 

- Minutes
- Hourly
- Daily
- Weekly

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Minutes, Hourly, Daily, Weekly

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurrenceValue
Specifies how often to make a backup.
This parameter uses the unit specified by the *RecurrenceType* parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionCount
Specifies the number of days to keep a backup.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartFromDateTime
Specifies the date from which to start making backups.
The default value is the current time.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### BackupScheduleUpdateRequest
This cmdlet returns a **BackupScheduleUpdateRequest** object that contains information about updated backup schedules.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleDeviceBackupScheduleAddConfig](.\New-AzureStorSimpleDeviceBackupScheduleAddConfig.md)

[Set-AzureStorSimpleDeviceBackupPolicy](.\Set-AzureStorSimpleDeviceBackupPolicy.md)

