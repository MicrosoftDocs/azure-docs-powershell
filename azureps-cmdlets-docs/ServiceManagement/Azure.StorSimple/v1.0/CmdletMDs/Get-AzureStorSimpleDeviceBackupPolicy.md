---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleDeviceBackupPolicy.md
schema: 2.0.0
---

# Get-AzureStorSimpleDeviceBackupPolicy

## SYNOPSIS
Gets backup policies.

## SYNTAX

```
Get-AzureStorSimpleDeviceBackupPolicy [-DeviceName] <String> [[-BackupPolicyName] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleDeviceBackupPolicy** cmdlet gets backup policies.
This cmdlet returns a **BackupPolicy** object or a list of all the **BackupPolicy** objects that belong to a device.
The backup policy objects contain the following properties: 

- **Name**
- **InstanceId**
- **BackupPolicyCreationType**
- **LastBackup**
- **NextBackup**
- **SchedulesCount**
- **SSMHostName**
- **VolumesCount**

## EXAMPLES

### Example 1: Get details for a policy
```
PS C:\>Get-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm" -BackupPolicyName "GeneralBackupPolicy07"
VERBOSE: ClientRequestId: 2a878cd6-8432-4646-8be8-a0cb0750958e_PS
VERBOSE: ClientRequestId: 00ea5a6d-8c27-4e22-b182-5969cdbb8033_PS
VERBOSE: ClientRequestId: 39dac9ff-4455-45ae-ae3d-7de1445b9520_PS


BackupSchedules          : {8658e3a2-8a59-4d43-8725-ab0c95665301}
Volumes                  : {testvolume03, testvolume05}
BackupPolicyCreationType : BySaaS
LastBackup               : 
NextBackup               : 16-12-2014 00:30:00
SchedulesCount           : 1
SSMHostName              : 
VolumesCount             : 2
InstanceId               : 84140a6a-9254-4fff-8d09-ae40e9f1bc7d
Name                     : GeneralBackupPolicy07
OperationInProgress      : None

VERBOSE: BackupPolicy with id 84140a6a-9254-4fff-8d09-ae40e9f1bc7d found!
```

This command gets a **BackupPolicyDetails** object named GeneralBackupPolicy07 on the device named Contoso63-AppVm.

### Example 2: Get a list of backup policies
```
PS C:\>Get-AzureStorSimpleDeviceBackupPolicy -DeviceName "Contoso63-AppVm"
InstanceId                           Name                               SchedulesCount VolumesCount                       BackupPolicyCreationType          LastBackup                        NextBackup                        SSMHostName                      
----------                           ----                               -------------- ------------                       ------------------------          ----------                        ----------                        -----------                      
13db29a4-bba9-4871-b872-db1fa0506b16 VG Clones                          1              2                                  BySaaS                            4/15/2015 8:30:02 AM              4/15/2015 8:30:00 PM                                               
2dcd3002-13c4-4bdb-a1ef-b35ce0a29416 vg-all                             1              4                                  BySaaS                            3/27/2015 9:12:15 PM              1/1/2010 5:30:00 AM                                                
54828d08-8309-4bd4-828f-21904863fb4c Cloud_Snapshot_Vol3_clone VG       1              1                                  BySaaS                            4/15/2015 9:00:03 AM              4/17/2015 9:00:30 AM                                               
6a51f39e-0ec9-4c57-8ec9-14a9255efa95 Test Group                         0              2                                  BySaaS                            3/27/2015 1:47:00 AM              1/1/2010 5:30:00 AM                                                
81c2db43-38f7-45fc-b2f2-476d1f6039a7 Cloud_Snapshot_Vol1_clone VG       1              1                                  BySaaS                            4/15/2015 7:30:02 AM              4/17/2015 7:30:00 AM                                               
82c4a5be-7473-431f-86e7-9db31ee9a9f8 Cloud_Snapshot_vg-all              1              4                                  BySaaS                            4/15/2015 11:30:02 AM             4/15/2015 3:30:00 PM                                               
cda96e83-3b38-4345-a56d-c8a96a0e57b3 Snapshot_vg-all                    1              4                                  BySaaS                            4/15/2015 1:30:02 PM              4/15/2015 3:30:00 PM
```

This command lists the **BackupPolicy** objects on the device named Contoso63-AppVm.

## PARAMETERS

### -BackupPolicyName
Specifies the name of the backup policy to get.
If you do not specify this parameter, this cmdlet gets all policies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Specifies the name of the StorSimple device on which to create the backup policy.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### IList<BackupPolicy>, BackupPolicyDetails
This cmdlet returns a **BackupPolicyDetails** object, if you specify the *BackupPolicyName* parameter.
If you do not specify that parameter, it returns an **IList\<BackupPolicy\>** object.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleDeviceBackupPolicy](.\New-AzureStorSimpleDeviceBackupPolicy.md)

[Remove-AzureStorSimpleDeviceBackupPolicy](.\Remove-AzureStorSimpleDeviceBackupPolicy.md)

[Set-AzureStorSimpleDeviceBackupPolicy](.\Set-AzureStorSimpleDeviceBackupPolicy.md)

