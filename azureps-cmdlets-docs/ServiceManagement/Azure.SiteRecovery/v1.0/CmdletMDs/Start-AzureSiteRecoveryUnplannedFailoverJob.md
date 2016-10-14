---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\Get-AzureSiteRecoveryJob.md
schema: 2.0.0
---

# Start-AzureSiteRecoveryUnplannedFailoverJob

## SYNOPSIS
Starts the Unplanned Failover operation for a protection entity or recovery plan.

## SYNTAX

### ByRPId (Default)
```
Start-AzureSiteRecoveryUnplannedFailoverJob -RPId <String> -Direction <String> [-PrimaryAction <Boolean>]
 [-PerformSourceSideActions] [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEId
```
Start-AzureSiteRecoveryUnplannedFailoverJob -ProtectionEntityId <String> -ProtectionContainerId <String>
 -Direction <String> [-PerformSourceSiteOperations <Boolean>] [-PerformSourceSideActions] [-WaitForCompletion]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRPObject
```
Start-AzureSiteRecoveryUnplannedFailoverJob -RecoveryPlan <ASRRecoveryPlan> -Direction <String>
 [-PrimaryAction <Boolean>] [-PerformSourceSideActions] [-WaitForCompletion] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByPEObject
```
Start-AzureSiteRecoveryUnplannedFailoverJob -ProtectionEntity <ASRProtectionEntity> -Direction <String>
 [-PerformSourceSiteOperations <Boolean>] [-PerformSourceSideActions] [-WaitForCompletion]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSiteRecoveryUnplannedFailoverJob** cmdlet starts the unplanned failover for a protection entity or for a recovery plan in Microsoft Azure Site Recovery.

Check whether the job succeeds by using the **Get-AzureSiteRecoveryJob** cmdlet.

## EXAMPLES

### Example 1: Start an unplanned failover job
```
PS C:\>$ProtectionContainer = Get-AzureSiteRecoveryProtectionContainer
PS C:\> $ProtectionEntity = Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer $ProtectionContainer 
PS C:\> Start-AzureSiteRecoveryUnplannedFailoverJob -ProtectionEntity $ProtectionEntity -Direction "PrimaryToRecovery"
ID               : c38eecdc-731c-405b-a61c-08db99aae2fe
ClientRequestId  : 32ace403-0916-4967-83a1-529176bd6e88-2014-49-06 15:49:24Z-P
State            : NotStarted
StateDescription : NotStarted
StartTime        :
EndTime          :
AllowedActions   : {}
Name             :
Tasks            : {}
Errors           : {}
```

The first command gets a protected container by using the **Get-AzureSiteRecoveryProtectionContainer** cmdlet, and then stores it in the $ProtectionContainer variable.

The second command gets the protected entities that belong to the protected container stored in $ProtectionContainer by using the **Get-AzureSiteRecoveryProtectionEntity** cmdlet.
The command stores the results in the $ProtectionEntity variable.

The final command starts the failover for the protected entities stored in $ProtectionEntity and specifies the direction of the failover.

## PARAMETERS

### -Direction
Specifies the direction of the failover.
Valid values are: 

- PrimaryToRecovery 
- RecoveryToPrimary

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForCompletion
Indicates that this cmdlet waits for the operation to complete before it returns control to the mshshort console.

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

### -RecoveryPlan
Specifies an **ASRRecoveryPlan** object for which to start the job.
To obtain an **ASRRecoveryPlan** object, use the **Get-AzureSiteRecoveryRecoveryPlan** cmdlet.

```yaml
Type: ASRRecoveryPlan
Parameter Sets: ByRPObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionEntity
Specifies an **ASRProtectionEntity** object for which to start the job.
To obtain an **ASRProtectionEntity** object, use the **Get-AzureSiteRecoveryProtectionEntity** cmdlet.

```yaml
Type: ASRProtectionEntity
Parameter Sets: ByPEObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionEntityId
Specifies the ID of a protected virtual machine for which to start the job.

```yaml
Type: String
Parameter Sets: ByPEId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionContainerId
Specifies the ID of a protected container.
This cmdlet starts the job for a protected virtual machine that belongs to the container that this cmdlet specifies.

```yaml
Type: String
Parameter Sets: ByPEId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PerformSourceSideActions
Indicates whether source site operations can be performed.

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

### -PerformSourceSiteOperations
Indicates whether source site operations can be performed.

```yaml
Type: Boolean
Parameter Sets: ByPEId, ByPEObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryAction
Indicates whether primary site actions are required.

```yaml
Type: Boolean
Parameter Sets: ByRPId, ByRPObject
Aliases: 

Required: False
Position: Named
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

### -RPId
Specifies the ID of a recovery plan for which to start the job.

```yaml
Type: String
Parameter Sets: ByRPId
Aliases: 

Required: True
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

[Get-AzureSiteRecoveryJob](.\Get-AzureSiteRecoveryJob.md)

[Get-AzureSiteRecoveryProtectionContainer](.\Get-AzureSiteRecoveryProtectionContainer.md)

[Get-AzureSiteRecoveryProtectionEntity](.\Get-AzureSiteRecoveryProtectionEntity.md)

