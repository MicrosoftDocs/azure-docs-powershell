---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: .\Start-AzureSiteRecoveryPlannedFailoverJob.md
schema: 2.0.0
---

# Start-AzureSiteRecoveryCommitFailoverJob

## SYNOPSIS
Starts a commit failover of the Azure Site Recovery object after failover.

## SYNTAX

### ByRPId (Default)
```
Start-AzureSiteRecoveryCommitFailoverJob -RPId <String> [-Direction <String>] [-WaitForCompletion]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByPEId
```
Start-AzureSiteRecoveryCommitFailoverJob -ProtectionEntityId <String> -ProtectionContainerId <String>
 [-Direction <String>] [-WaitForCompletion] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByRPObject
```
Start-AzureSiteRecoveryCommitFailoverJob -RecoveryPlan <ASRRecoveryPlan> [-Direction <String>]
 [-WaitForCompletion] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByPEObject
```
Start-AzureSiteRecoveryCommitFailoverJob -ProtectionEntity <ASRProtectionEntity> [-Direction <String>]
 [-WaitForCompletion] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSiteRecoveryCommitFailoverJob** cmdlet starts a commit failover of the Microsoft Azure Site Recovery object after failover.
This cmdlet starts the operation and returns the job object.
Check whether the job succeeds by using the **Get-AzureSiteRecoveryJob** cmdlet.

## EXAMPLES

### Example 1: Start a commit failover job
```
PS C:\>$Container = Get-AzureSiteRecoveryProtectionContainer 
PS C:\> $Protected = Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer $Container 
PS C:\> Start-AzureSiteRecoveryCommitFailoverJob -ProtectionEntity $Protected
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

The first command gets all protected containers for the current Azure Site Recovery vault by using the **Get-AzureSiteRecoveryProtectionContainer** cmdlet, and then stores the results in the $Container variable.

The second command gets the protected vitural machines that belong to the container stored in $Container by using the **Get-AzureSiteRecoveryProtectionEntity** cmdlet.
The command stores the results in the $Protected variable.

The final command starts the failover job for the protected objects stored in $Protected.

## PARAMETERS

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

### -WaitForCompletion
Indicates that this cmdlet waits for the operation to complete before it returns control to the Windows PowerShell console.

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
Specifies a recovery plan object for which to start the job.
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

### -Direction
Specifies the direction.

```yaml
Type: String
Parameter Sets: (All)
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
Type: AzureProfile
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

[Start-AzureSiteRecoveryPlannedFailoverJob](.\Start-AzureSiteRecoveryPlannedFailoverJob.md)

[Start-AzureSiteRecoveryUnplannedFailoverJob](.\Start-AzureSiteRecoveryUnplannedFailoverJob.md)

[Get-AzureSiteRecoveryJob](.\Get-AzureSiteRecoveryJob.md)

[Get-AzureSiteRecoveryProtectionContainer](.\Get-AzureSiteRecoveryProtectionContainer.md)

[Get-AzureSiteRecoveryProtectionEntity](.\Get-AzureSiteRecoveryProtectionEntity.md)

