---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan.md
schema: 2.0.0
---

# Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan

## SYNOPSIS
Gets migration plans for legacy containers.

## SYNTAX

```
Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan [[-LegacyConfigId] <String>]
 [[-LegacyContainerNames] <String[]>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleLEgacyVolumeContainerMigrationPlan** cmdlet gets migration plans for legacy containers.
Specify a migration plan by its legacy configuration ID.
If creation of the migration plan is still in progress, this cmdlet gets the status of the migration plan.
If the migration plan is completed, this cmdlet returns the actual migration plan for the set of legacy containers.
If you do not specify the *LegacyConfigId* parameter, this cmdlet returns a list of configuration IDs.

## EXAMPLES

### Example 1: Get the status of a plan
```
PS C:\>Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan -LegacyConfigId "f16463bd-94a9-4c3c-91c2-7a3ba7120087" -LegacyContainerNames "OneSDKAzureCloud"
VERBOSE: 2015-04-08 13:48:05 ClientRequestId: 51e413fd-c2c9-4108-88cd-a0e792eab80a_PS
VERBOSE: 2015-04-08 13:48:05 ClientRequestId: 4c6398ef-35a0-4d1c-931e-d9d45599a97a_PS
VERBOSE: 2015-04-08 13:48:17 ClientRequestId: ef7a7e35-6dff-46cd-9df3-cb5fa25d149e_PS
VERBOSE: Request Id : fd7e502f273885468f633a44567bcb3f, HttpResponse OK
VERBOSE: List of volume containers: 


LegacyConfigId                    : f16463bd-94a9-4c3c-91c2-7a3ba7120087
DeviceName                        : ARUNKM-N4
MigrationTimeEstimationCompleted  : CloudConfigurationName        : OneSDKAzureCloud
                                    EstimatedTimeForLatestBackup  : 15Minutes
                                    EstimatedTimeForAllBackups    : 15Minutes
                                    These estimates are assuming 20 MBps bandwidth. Refer to migration guide to re-calculate for lower bandwidths. 



MigrationTimeEstimationInProgress : None
MigrationTimeEstimationFailed     : None
MigrationTimeEstimationNotStarted : None
```

This command gets the status of the migration plan.
The status includes assumed bandwidth, estimated time and, related information.

### Example 2: Get the IDs of existing plans
```
PS C:\>Get-AzureStorSimpleLegacyVolumeContainerMigrationPlan
VERBOSE: 2015-04-08 13:46:51 ClientRequestId: 813da56c-0cfc-4325-80db-08ef32bdde1e_PS
VERBOSE: 2015-04-08 13:46:51 ClientRequestId: 9e7cf244-1894-490a-be02-749834a99318_PS
VERBOSE: List of LegacyConfig Ids on the resource: 

LegacyConfigId                                              DeviceName
--------------                                              ----------
1e1f10a0-3dff-4249-b847-4930061cd87a                        ARUNKM-N4
26d4096d-49b6-4102-b188-0446ece73c8b                        ARUNKM-N4
```

This command gets all the configuration IDs of migration plans.

## PARAMETERS

### -LegacyConfigId
Specifies the unique ID of the configuration of the legacy appliance.

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

### -LegacyContainerNames
Specifies an array of volume container names for which this cmdlet gets a migration plan.

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

### MigrationPlanMsg
This cmdlet returns a **MigrationPlanMsg** object that contains the status of the migration plan job, assumed bandwidth in megabits per second, and estimated time in minutes.

## NOTES

## RELATED LINKS

[Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan](.\Start-AzureStorSimpleLegacyVolumeContainerMigrationPlan.md)

