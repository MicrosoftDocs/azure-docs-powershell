---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Confirm-AzureStorSimpleLegacyVolumeContainerStatus.md
schema: 2.0.0
---

# Get-AzureStorSimpleLegacyVolumeContainerConfirmStatus

## SYNOPSIS
Gets the status of a commit or rollback operation.

## SYNTAX

```
Get-AzureStorSimpleLegacyVolumeContainerConfirmStatus [-LegacyConfigId] <String>
 [[-LegacyContainerNames] <String[]>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleLegacyVolumeContainerConfirmStatus** cmdlet gets the status of the commit or rollback operation.

## EXAMPLES

### Example 1: Get the status of a completed commit operation
```
PS C:\>Get-AzureStorSimpleLegacyVolumeContainerConfirmStatus -LegacyConfigId "f16463bd-94a9-4c3c-91c2-7a3ba7120087" -LegacyContainerNames "OneSDKAzureCloud"
VERBOSE: 2015-04-08 13:51:01 ClientRequestId: 2bda2b9b-1361-4787-bc04-1e081218ed76_PS
VERBOSE: 2015-04-08 13:51:01 ClientRequestId: 84bf18d8-c459-47a7-b4a8-f82ca8659672_PS
VERBOSE: 2015-04-08 13:51:12 ClientRequestId: e93f9cb7-df58-497e-bb9f-9a6a23e68925_PS


LegacyConfigId             : f16463bd-94a9-4c3c-91c2-7a3ba7120087
CommitComplete             : CloudConfigurationName : OneSDKAzureCloud
                             Operation              : Commit
                             PercentageCompleted    : 100
                             Messages               : 

CommitInProgress           : None
CommitFailed               : None
RollbackComplete           : None
RollbackInProgress         : None
RollbackFailed             : None
CommitOrRollbackNotStarted : None
```

This command gets the status of a commit operation for the named container.
This operation has a status of completed.

### Example 2: Get the status of a completed rollback operation
```
PS C:\>Get-AzureStorSimpleLegacyVolumeContainerConfirmStatus -LegacyConfigId "f16463bd-94a9-4c3c-91c2-7a3ba7120087" -LegacyContainerNames "OneSDKAzureCloud"
VERBOSE: 2015-04-08 13:51:01 ClientRequestId: 2bda2b9b-1361-4787-bc04-1e081218ed76_PS
VERBOSE: 2015-04-08 13:51:01 ClientRequestId: 84bf18d8-c459-47a7-b4a8-f82ca8659672_PS
VERBOSE: 2015-04-08 13:51:12 ClientRequestId: e93f9cb7-df58-497e-bb9f-9a6a23e68925_PS


LegacyConfigId             : f16463bd-94a9-4c3c-91c2-7a3ba7120087
CommitComplete             : None
CommitInProgress           : None
CommitFailed               : None
RollbackComplete           : CloudConfigurationName : OneSDKAzureCloud
                             Operation              : Rollback
                             PercentageCompleted    : 100
                             Messages               : 

RollbackInProgress         : None
RollbackFailed             : None
CommitOrRollbackNotStarted : None
```

This command gets the status of a rollback operation for the named container.
This operation has a status of completed.

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

### None

## OUTPUTS

### ConfirmMigrationStatusMsg
This cmdlet returns the status of the confirm migration operation that is performed.

## NOTES

## RELATED LINKS

[Confirm-AzureStorSimpleLegacyVolumeContainerStatus](.\Confirm-AzureStorSimpleLegacyVolumeContainerStatus.md)

[Get-AzureStorSimpleLegacyVolumeContainerStatus](.\Get-AzureStorSimpleLegacyVolumeContainerStatus.md)

