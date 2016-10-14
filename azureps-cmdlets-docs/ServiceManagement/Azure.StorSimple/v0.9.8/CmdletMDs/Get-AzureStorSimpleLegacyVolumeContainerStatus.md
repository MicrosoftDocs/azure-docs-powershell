---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Confirm-AzureStorSimpleLegacyVolumeContainerStatus.md
schema: 2.0.0
---

# Get-AzureStorSimpleLegacyVolumeContainerStatus

## SYNOPSIS
Gets the migration status of the volume containers.

## SYNTAX

```
Get-AzureStorSimpleLegacyVolumeContainerStatus [-LegacyConfigId] <String> [[-LegacyContainerNames] <String[]>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleLegacyVolumeContainerStatus** cmdlet gets the migration status of the volume containers.
This cmdlet returns status information which includes whether the volume container migration is still in progress, completed, or failed.

## EXAMPLES

### Example 1: Get status for a failed migration
```
PS C:\>Get-AzureStorSimpleLegacyVolumeContainerStatus -LegacyConfigId "dcddbb51-2ab2-4d22-8204-fefdbd6b7ba4" -LegacyContainerNames "OneSDKAzureCloud"
ConfigId             : dcddbb51-2ab2-4d22-8204-fefdbd6b7ba4
MigrationCompleted   : No Cloud Configuration(s) are found to be in Completed state of Migration
MigrationInprogress  : No Cloud Configuration(s)  are found to be in InProgress state of Migration
MigrationNotStarted  : No Cloud Configuration(s) are found to be in NotStarted state of Migration
MigrationFailed      : Cloud Configuration Name: OneSDKAzureCloud
                       PercentageCompleted : 0
                       MigrationStatus : Failed
                       No Backup sets found
```

This command gets the migration status for the named legacy container.
The results show that the migration failed.

### Example 2: Get status for a migration in progress
```
PS C:\>Get-AzureStorSimpleLegacyVolumeContainerStatus -LegacyConfigId "dcddbb51-2ab2-4d22-8204-fefdbd6b7ba4" -LegacyContainerNames "OneSDKAzureCloud"
ConfigId             : 5a83ec88-9e0a-4722-9fb0-9131caa7387a
MigrationCompleted   : No Cloud Configuration(s) are found to be in Completed state of Migration
MigrationInprogress  : CloudConfigurationName: OneSDKAzureCloud
                       PercentageCompleted : 10
                       MigrationStatus : InProgress
                       BackupSets : 
                           Policy : OneSDKBackupPolicy, Status : InProgress
MigrationNotStarted  : No Cloud Configuration(s) are found to be in NotStarted state of Migration
MigrationFailed      : No Cloud Configuration(s) are found to be in Failed state of Migration
```

This command gets the migration status for the named legacy container.
The results show that the migration is in progress.

### Example 3: Get status for a completed migration
```
PS C:\>Get-AzureStorSimpleLegacyVolumeContainerStatus -LegacyConfigId dcddbb51-2ab2-4d22-8204-fefdbd6b7ba4 -LegacyContainerNames OneSDKAzureCloud
ConfigId             : 5a83ec88-9e0a-4722-9fb0-9131caa7387a
MigrationCompleted   : Cloud ConfigurationName: OneSDKAzureCloud
                       PercentageCompleted : 100
                       MigrationStatus : Completed
                       BackupSets : 
                          Policy : vg1p1, Created On : 04/06/2015 11:22:00, Status : Completed
                          Policy : vg1p1, Created On : 03/30/2015 11:22:00, Status : Completed
                          Policy : c1v1-Auto-Daily-CloudSnapshot, Created On : 03/30/2015 03:30:00, Status : Completed
MigrationInprogress  : No Cloud Configuration(s) are found to be in InProgress state of Migration
MigrationNotStarted  : No Cloud Configuration(s) are found to be in NotStarted state of Migration
MigrationFailed      : No Cloud Configuration(s) are found to be in Failed state of Migration
```

This command gets the migration status for the named legacy container.
The results show that the migration is completed.

## PARAMETERS

### -LegacyConfigId
Specifies the unique ID of the configuration of the legacy appliance.

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

### -LegacyContainerNames
Specifies an array of volume container names for which the migration plan applies.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Confirm-AzureStorSimpleLegacyVolumeContainerStatus](.\Confirm-AzureStorSimpleLegacyVolumeContainerStatus.md)

[Get-AzureStorSimpleLegacyVolumeContainerConfirmStatus](.\Get-AzureStorSimpleLegacyVolumeContainerConfirmStatus.md)

