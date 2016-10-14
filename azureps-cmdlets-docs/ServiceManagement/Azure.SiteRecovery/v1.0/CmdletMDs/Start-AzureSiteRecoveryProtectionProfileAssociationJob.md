---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\Start-AzureSiteRecoveryProtectionProfileDissociationJob.md
schema: 2.0.0
---

# Start-AzureSiteRecoveryProtectionProfileAssociationJob

## SYNOPSIS
Starts a job to associate a protection profile to protection containers.

## SYNTAX

### EnterpriseToAzure (Default)
```
Start-AzureSiteRecoveryProtectionProfileAssociationJob -ProtectionProfile <ASRProtectionProfile>
 -PrimaryProtectionContainer <ASRProtectionContainer> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### EnterpriseToEnterprise
```
Start-AzureSiteRecoveryProtectionProfileAssociationJob -ProtectionProfile <ASRProtectionProfile>
 -PrimaryProtectionContainer <ASRProtectionContainer> -RecoveryProtectionContainer <ASRProtectionContainer>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSiteRecoveryProtectionProfileAssociationJob** cmdlet starts a job to associate a protection profile to a protection container, or a protection container and a recovery protection container.

## EXAMPLES

### Example 1: Associate a protection profile
```
PS C:\>$ProtectionContainer01 = Get-AzureSiteRecoveryProtectionContainer -Id "5ba2ea95-856d-4033-9ca3-91e3e2c080b9"
PS C:\> $ProtectionProfile = New-AzureSiteRecoveryProtectionProfileObject -ReplicationProvider HyperVReplica -AllowReplicaDeletion -ApplicationConsistentSnapshotFrequencyInHours 1 -CompressionEnabled -RecoveryPoints 2 -ReplicationFrequencyInSeconds 30 -ReplicationMethod Online -ReplicationPort 8085 -ReplicationStartTime 1
PS C:\> $ProtectionContainer02 = Get-AzureSiteRecoveryProtectionContainer -Id "cf011f2a-aa19-443c-9f60-357f6b8afb77"
PS C:\> Start-AzureSiteRecoveryProtectionProfileAssociationJob -PrimaryProtectionContainer $ProtectionContainer01 -ProtectionProfile $ProtectionProfile -RecoveryProtectionContainer $ProtectionContainer02
Name             : MyProtectionProfile
ID               : 51978b0f-9241-4153-9171-2e19344f0805
ClientRequestId  : bb6f3200-b7c6-4c6f-bcbc-a70bb9946f03-2015-01-27 22:55:55Z-P
State            : InProgress
StateDescription : InProgress
StartTime        : 1/27/2015 10:56:01 PM
EndTime          : 
AllowedActions   : 
Tasks            : {Adding the protection group, Configuring Windows Server 2012 R2 Hyper-V hosts for Azure}
Errors           : {}
```

The first command gets a protection container by using the **Get-AzureSiteRecoveryProtectionContainer** cmdlet, and then stores that container in the $ProtectionContainer01 variable.

The second command creates a protection profile by using the **New-AzureSiteRecoveryProtectionProfileObject** cmdlet, and stores that protection profile in the $ProtectionProfile variable.

The third command gets a protection container, and then stores it in the $ProtectionContainer02 variable.

The final command associates the protection profile stored in $ProtectionProfile to the container stored in $ProtectionContainer01 as the primary protection container.
The command associates the container stored in $ProtectionContainer02 as the recovery protection container.

## PARAMETERS

### -ProtectionProfile
Specifies the protection profile settings to apply to the protection containers.
To obtain an **ASRProtectionProfile** object, use the **New-AzureSiteRecoveryProtectionProfileObject** cmdlet.

```yaml
Type: ASRProtectionProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrimaryProtectionContainer
Specifies the primary protection container to which to apply the protection profile.
To obtain an **ASRProtectionContainer** protection container object, use the **Get-AzureSiteRecoveryProtectionContainer** cmdlet.

```yaml
Type: ASRProtectionContainer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryProtectionContainer
Specifies the recovery protection container to which to apply the protection profile.
To obtain an **ASRProtectionContainer** protection container object, use **Get-AzureSiteRecoveryProtectionContainer**.

```yaml
Type: ASRProtectionContainer
Parameter Sets: EnterpriseToEnterprise
Aliases: 

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-AzureSiteRecoveryProtectionProfileDissociationJob](.\Start-AzureSiteRecoveryProtectionProfileDissociationJob.md)

[Get-AzureSiteRecoveryProtectionContainer](.\Get-AzureSiteRecoveryProtectionContainer.md)

[New-AzureSiteRecoveryProtectionProfileObject](.\New-AzureSiteRecoveryProtectionProfileObject.md)

