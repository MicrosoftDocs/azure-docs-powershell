---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Remove-AzureStorSimpleDeviceBackup.md
schema: 2.0.0
---

# Get-AzureStorSimpleDeviceBackup

## SYNOPSIS
Gets backups from a device.

## SYNTAX

### Empty (Default)
```
Get-AzureStorSimpleDeviceBackup [-DeviceName] <String> [[-From] <String>] [[-To] <String>] [-First <Int32>]
 [-Skip <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyById
```
Get-AzureStorSimpleDeviceBackup [-DeviceName] <String> [-BackupPolicyId] <String> [[-From] <String>]
 [[-To] <String>] [-First <Int32>] [-Skip <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyById2
```
Get-AzureStorSimpleDeviceBackup [-DeviceName] <String> [-VolumeId] <String> [[-From] <String>] [[-To] <String>]
 [-First <Int32>] [-Skip <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject
```
Get-AzureStorSimpleDeviceBackup [-DeviceName] <String> [-BackupPolicy] <BackupPolicyDetails> [[-From] <String>]
 [[-To] <String>] [-First <Int32>] [-Skip <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByObject2
```
Get-AzureStorSimpleDeviceBackup [-DeviceName] <String> [-Volume] <VirtualDisk> [[-From] <String>]
 [[-To] <String>] [-First <Int32>] [-Skip <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleDeviceBackup** cmdlet gets backups from a device.
You can specify the backup policy, volume, and creation time for backups.

This cmdlet can return a maximum of 100 backups in the first page.
If more than 100 backups exist, retrieve subsequent pages by using the *First* and *Skip* parameters.
If you specify a value of 100 for *Skip* and 50 for *First*, this cmdlet does not return the first 100 results.
It returns the next 50 results after the 100 that it skips.

## EXAMPLES

### Example 1: Get all backups on a device
```
PS C:\>Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm"
InstanceId                           Name                               Type          BackupJobCreationType              CreatedOn                          SizeInBytes                       Snapshots                         SSMHostName                      
----------                           ----                               ----          ---------------------              ---------                          -----------                       ---------                         -----------                      
85074062-ef6a-408a-b6c9-2a0904bb99ca Snapshot_vg-all                    LocalSnapshot BySchedule                         4/15/2015 1:30:02 PM               9375913607168                     {Volume 1, Volume 4, Volume 3,                                     
                                                                                                                                                                                              Volume 2}                                                          
ebd87fa3-a9e2-49c9-a7e6-dada47071544 Cloud_Snapshot_vg-all              CloudSnapshot BySchedule                         4/15/2015 11:30:02 AM              9375913607168                     {Volume 1, Volume 4, Volume 3,                                     
                                                                                                                                                                                              Volume 2}                                                          
9f7a03be-8c39-474c-bf88-b2c7b54e833c Cloud_Snapshot_Vol3_clone VG       CloudSnapshot BySchedule                         4/15/2015 9:00:03 AM               1717986918400                     {Volume 3 Clone}                                                   
177b2dad-c0b2-42d6-b7bb-16926e54e9c6 VG Clones                          CloudSnapshot BySchedule                         4/15/2015 8:30:02 AM               5016521801728                     {Volume 1 Clone, Volume 3 Clone}                                   
49c470c0-eadb-40ac-9928-94018a8edcd4 Cloud_Snapshot_Vol1_clone VG       CloudSnapshot BySchedule                         4/15/2015 7:30:02 AM               3298534883328                     {Volume 1 Clone}                                                   
45dfd283-f924-4b45-93eb-b20650cadf43 vg-all                             LocalSnapshot Adhoc                              3/27/2015 9:12:15 PM               9375913607168                     {Volume 1, Volume 4, Volume 3,                                     
                                                                                                                                                                                              Volume 2}                                                          
2c3dd48d-824c-4298-82b5-fb44abb67a1e Test Group                         LocalSnapshot Adhoc                              3/27/2015 1:47:00 AM               5016521801728                     {Volume 1, Volume 3}
```

This command gets all backups that exist on the device named Contoso63-AppVm.
If there are more than the maximum of 100 backups allowed for the first page, use the *First* and *Skip* parameters to view additional results.

### Example 2: Get backups created between two dates
```
PS C:\>Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -From "9/7/2014" -To "10/7/2014" -First 2 -Skip 1
BackupJobCreationType : BySchedule
CreatedOn             : 10/5/2014 11:00:04 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : ec2fdf5c-c807-4f7b-a942-d4c4a9b68c44
Name                  : ContosoTSQA_Default
BackupJobCreationType : BySchedule
CreatedOn             : 10/4/2014 11:00:06 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : 5ac4f947-f4c6-4770-9000-2242e72fc6d3
Name                  : ContosoTSQA_DefaultVERBOSE: # of backups returned : 2
VERBOSE: More backups are available for your query. To access the next page of your result use \"-First 2 -Skip 3\" in
your commandlet
```

This command gets backups on the device named Contoso63-AppVm that were created on or after 10/7/2014 and on or before 10/8/2014.
This cmdlet skips the first result and returns the first two results after that first result.
Modify values for *First* and *Skip* to view other results.

### Example 3: Get backups for a backup policy ID
```
PS C:\>Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -BackupPolicyId "de088eac-b283-4d92-b501-a759845fdf3f" -First 10 -From "9/7/2014"
BackupJobCreationType : BySchedule
CreatedOn             : 10/1/2014 11:00:12 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : e1aec9f1-a321-443f-a058-ba78c749c2c2
Name                  : ContosoTSQA_Default
....... 

BackupJobCreationType : BySchedule
CreatedOn             : 9/29/2014 11:00:12 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : f8041928-37b9-4048-a99c-2d3078943874
Name                  : ContosoTSQA_Default
VERBOSE: # of backups returned : 10
VERBOSE: More backups are available for your query. To access the next page of your result use \"-First 10 -Skip 10\"
in your commandlet
```

This command gets backups on the device named Contoso63-AppVm created on or before the specified date.
The command gets backups that were created by using the backup policy that has the specified ID.
This command specifies the *First* parameter, so it returns only the first 10 results.

### Example 4: Get backups for a backup policy object
```
PS C:\>Get-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyName "TSQATest_Default" | Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -First 10 -From "9/7/2014"
BackupJobCreationType : BySchedule
CreatedOn             : 10/1/2014 11:00:12 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : e1aec9f1-a321-443f-a058-ba78c749c2c2
Name                  : ContosoTSQA_Default
....... 

BackupJobCreationType : BySchedule
CreatedOn             : 9/29/2014 11:00:12 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : f8041928-37b9-4048-a99c-2d3078943874
Name                  : ContosoTSQA_Default
VERBOSE: # of backups returned : 10
VERBOSE: More backups are available for your query. To access the next page of your result use \"-First 10 -Skip 10\"
in your commandlet
```

This command gets a **BackupPolicyDetails** object by using the **Get-AzureStorSimpleDeviceBackupPolicy** cmdlet, and then passes that object to the current cmdlet by using the pipeline operator.
That cmdlet gets backups for the device named Contoso63-AppVm created by using the backup policy from the first part of the command.
The command gets backups created on or before the specified date, just as in the previous example.
This command returns only the first 10 results.

### Example 5: Get a backup for a volume ID
```
PS C:\>Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -VolumeId "SS-VOL-246b9df1-11bb-4071-8043-f955cc406446" -First 1
BackupJobCreationType : BySchedule
CreatedOn             : 10/9/2014 11:00:10 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : 4fef4178-0145-404b-8257-7d958a380b8b
Name                  : ContosoTSQA_Default

VERBOSE: # of backups returned : 1
VERBOSE: No more backup sets are present for your query!
```

This command gets a backup on the device that is created on the volume that has the specified instance ID.
This command specifies the *First* parameter, so it returns only the first one result.

### Example 6: Get a backup for a volume name
```
PS C:\>Get-AzureStorSimpleDeviceVolume -DeviceName "Contoso63-AppVm" -VolumeName "TSQATest03" | Get-AzureStorSimpleDeviceBackup -DeviceName "Contoso63-AppVm" -First 1
BackupJobCreationType : BySchedule
CreatedOn             : 10/9/2014 11:00:10 AM
SizeInBytes           : 10737418240
Snapshots             : {ContosoTSQA}
SSMHostName           : 
Type                  : CloudSnapshot
InstanceId            : 4fef4178-0145-404b-8257-7d958a380b8b
Name                  : ContosoTSQA_Default

VERBOSE: # of backups returned : 1
VERBOSE: No more backup sets are present for your query!
```

This command gets a **VirtualDisk** object by using the **Get-AzureStorSimpleDeviceVolume** cmdlet, and then passes that object to the current cmdlet by using the pipeline operator.
That cmdlet gets backups for the device named Contoso63-AppVm created on the volume from the first part of the command.
This command returns only the first result.

## PARAMETERS

### -BackupPolicy
Specifies a **BackupPolicyDetails** object.
This cmdlet uses the **InstanceId** of this object to determine which backups to get.
To obtain a **BackupPolicyDetails** object, use the **Get-AzureStorSimpleDeviceBackupPolicy** cmdlet.

```yaml
Type: BackupPolicyDetails
Parameter Sets: IdentifyByObject
Aliases: BackupPolicyDetails

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupPolicyId
Specifies an instance ID of a backup policy.
This cmdlet gets device backups for policy that this parameter specifies.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device for which to get backups.

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

### -From
Specifies the start date and time for the backups that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### -To
Specifies the end date and time for the backups that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Volume
Specifies a **VirtualDisk** object.
This cmdlet uses the **InstanceId** of this object to determine the volume in which backups exist.
To obtain a **VirtualDisk** object, use the **Get-AzureStorSimpleDeviceVolume** parameter.

```yaml
Type: VirtualDisk
Parameter Sets: IdentifyByObject2
Aliases: VirtualDiskInfo

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeId
Specifies the instance ID of the volume in which backups exist.

```yaml
Type: String
Parameter Sets: IdentifyById2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First
psdx_firstdesc

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
psdx_skipdesc

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

### BackupPolicyDetails, VirtualDisk
This cmdlet accepts **BackupPolicyDetails** and **VirtualDisk** objects.

## OUTPUTS

### IList<Backup>
This cmdlet returns a list of **Backup** objects.

## NOTES

## RELATED LINKS

[Remove-AzureStorSimpleDeviceBackup](.\Remove-AzureStorSimpleDeviceBackup.md)

[Get-AzureStorSimpleDeviceBackupPolicy](.\Get-AzureStorSimpleDeviceBackupPolicy.md)

[Get-AzureStorSimpleDeviceVolume](.\Get-AzureStorSimpleDeviceVolume.md)

