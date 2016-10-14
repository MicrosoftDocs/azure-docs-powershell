---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Stop-AzureStorSimpleJob.md
schema: 2.0.0
---

# Get-AzureStorSimpleJob

## SYNOPSIS
Gets StorSimple jobs.

## SYNTAX

```
Get-AzureStorSimpleJob [[-DeviceName] <String>] [[-InstanceId] <String>] [[-Status] <String>]
 [[-Type] <String>] [[-From] <DateTime>] [[-To] <DateTime>] [-Skip <Int32>] [-First <Int32>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleJob** cmdlet gets Azure StorSimple jobs.
Specify an instance ID to get a specific job.
Specify other parameters to limit the jobs that this cmdlet gets.

This cmdlet can return a maximum of 200 jobs.
If more than 200 jobs exist, get the remaining jobs by using the *First* and *Skip* parameters.
If you specify a value of 100 for *Skip* and 50 for *First*, this cmdlet does not return the first 100 results.
It returns the next 50 results after the 100 that it skips.

## EXAMPLES

### Example 1: Get a job by using an ID
```
PS C:\>Get-AzureStorSimpleJob -InstanceId "574f47e0-44e9-495c-b8a5-0203c57ebf6d"
BackupPolicy             : 
BackupTimeStamp          : 1/1/0001 12:00:00 AM
BackupType               : CloudSnapshot
DataStats                : Microsoft.WindowsAzure.Management.StorSimple.Models.DataStatistics
Device                   : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
Entity                   : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
ErrorDetails             : {}
HideProgressDetails      : False
InstanceId               : 574f47e0-44e9-495c-b8a5-0203c57ebf6d
IsInstantRestoreComplete : False
IsJobCancellable         : True
JobDetails               : Microsoft.WindowsAzure.Management.StorSimple.Models.JobStatusInfo
Name                     : 26447caf-59bb-41c9-a028-3224d296c7dc
Progress                 : 100
SourceDevice             : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
SourceEntity             : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
SourceVolume             : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
Status                   : Completed
TimeStats                : Microsoft.WindowsAzure.Management.StorSimple.Models.TimeStatistics
Type                     : Backup
Volume                   : Microsoft.WindowsAzure.Management.StorSimple.Models.CisBaseObject
```

This command gets information for the job that has the specified ID.

### Example 2: Get jobs by using a device name
```
PS C:\>Get-AzureStorSimpleJob -DeviceName "8600-Bravo 001" -First 2
InstanceId                           Type                         Status                                          DeviceName                                      StartTime                                       Progress                                       
----------                           ----                         ------                                          ----------                                      ---------                                       --------                                       
1997c33f-bfcc-4d08-9aba-28068340a1f9 Backup                       Running                                         8600-Bravo 001                                  4/15/2015 1:30:02 PM                            92                                             
85074062-ef6a-408a-b6c9-2a0904bb99ca Backup                       Completed                                       8600-Bravo 001                                  4/15/2015 1:30:02 PM                            100
```

This command gets information for the jobs for the device named 8600-Bravo 001.
The command gets the first two jobs for the device.

### Example 3: Get completed jobs
```
PS C:\>Get-AzureStorSimpleJob -Status Completed -Skip 10 -First 2
```

This command gets completed jobs.
The command gets only the first two jobs after it skips the first ten jobs.

### Example 4: Get manual backup jobs
```
PS C:\>Get-AzureStorSimpleJob -Type ManualBackup
```

This command gets jobs of the manual backup type.

### Example 5: Get jobs between specified times
```
PS C:\>$StartTime = Get-Date -Year 2015 -Month 3 -Day 10
PS C:\> $EndTime = Get-Date -Year 2015 -Month 3 -Day 11 -Hour 12 -Minute 15
PS C:\>Get-AzureStorSimpleJob -DeviceName "Device07" -From $StartTime -To $EndTime
```

The first two commands create **DateTime** objects by using the **Get-Date** cmdlet.
The commands store the new times in the $StartTime and $EndTime variables.
For more information, type `Get-Help Get-Date`.

The final command gets jobs for the device named Device07 between the times stored in $StartTime and $EndTime.

## PARAMETERS

### -DeviceName
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -From
@{Text=}

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
@{Text=}

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

### -Status
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Running, Completed, Cancelled, Failed, Cancelling, CompletedWithErrors

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -To
@{Text=}

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Backup, ManualBackup, Restore, CloneWorkflow, DeviceRestore, Update, SupportPackage, VirtualApplianceProvisioning

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First
Gets only the specified number of objects.
Enter the number of objects to get.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skip
Ignores the specified number of objects and then gets the remaining objects.
Enter the number of objects to skip.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
You cannot pipe input to this cmdlet.

## OUTPUTS

### IList<DeviceJobDetails>, DeviceJobDetails
This cmdlet returns a list of job details objects, or, if you specify the *InstanceID* parameter, it returns a single job detail object.

## NOTES

## RELATED LINKS

[Stop-AzureStorSimpleJob](.\Stop-AzureStorSimpleJob.md)

