---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleDeviceBackupScheduleUpdateConfig.md
schema: 2.0.0
---

# New-AzureStorSimpleDeviceBackupScheduleAddConfig

## SYNOPSIS
Creates a backup schedule configuration object.

## SYNTAX

```
New-AzureStorSimpleDeviceBackupScheduleAddConfig [-BackupType] <String> [-RecurrenceType] <String>
 [-RecurrenceValue] <Int32> [-RetentionCount] <Int64> [[-StartFromDateTime] <String>] [-Enabled] <Boolean>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorSimpleDeviceBackupScheduleAddConfig** cmdlet creates a **BackupScheduleBase** configuration object.
Use this configuration object to create new backup policy by using the **New-AzureStorSimpleDeviceBackupPolicy** cmdlet.

## EXAMPLES

### Example 1: Create a backup configuration object
```
PS C:\>New-AzureStorSimpleDeviceBackupScheduleAddConfig -BackupType CloudSnapshot -RecurrenceType Daily -RecurrenceValue 1 -RetentionCount 100 -Enabled $True
VERBOSE: ClientRequestId: 426a79ee-fed3-4d3d-9123-e371f83222b3_PS


BackupType     : CloudSnapshot
Recurrence     : Microsoft.WindowsAzure.Management.StorSimple.Models.ScheduleRecurrence
RetentionCount : 100
StartTime      : 2014-12-16T00:37:19+05:30
Status         : Enabled
```

This command creates a backup schedule base object for cloud snapshot backups.
The backup occurs every day, and the backups are kept for 100 days.
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
Position: 1
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

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an azure_2 profile.

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
Position: 2
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
Position: 3
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
Position: 4
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
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### BackupScheduleBase
This cmdlet returns a **BackupScheduleBase** object.
Use a **BackupScheduleBase** to construct new backup policy.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleDeviceBackupScheduleUpdateConfig](.\New-AzureStorSimpleDeviceBackupScheduleUpdateConfig.md)

[New-AzureStorSimpleDeviceBackupPolicy](.\New-AzureStorSimpleDeviceBackupPolicy.md)

