---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 9AE41884-C39F-4AEB-8030-96167F98C8DD
online version: 
schema: 2.0.0
---

# Start-AzureSiteRecoveryTestFailoverJob

## SYNOPSIS
Starts a test failover for a Site Recovery protection entity.

## SYNTAX

### ByPEId (Default)
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>] -Direction <String>
 -ProtectionEntityId <String> -ProtectionContainerId <String> [-WaitForCompletion] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByRPId
```
Start-AzureSiteRecoveryTestFailoverJob -RpId <String> [-Network <ASRNetwork>] [-NetworkType <String>]
 -Direction <String> [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRPIdWithLogicalNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob -RpId <String> [-Network <ASRNetwork>] [-NetworkType <String>]
 -Direction <String> [-WaitForCompletion] -LogicalNetworkId <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByRPIdWithVMNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob -RpId <String> [-Network <ASRNetwork>] [-NetworkType <String>]
 -Direction <String> [-WaitForCompletion] -VmNetworkId <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByRPIdWithVMNetwork
```
Start-AzureSiteRecoveryTestFailoverJob -RpId <String> -Network <ASRNetwork> [-NetworkType <String>]
 -Direction <String> [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEObjectWithVMNetwork
```
Start-AzureSiteRecoveryTestFailoverJob -Network <ASRNetwork> [-NetworkType <String>] -Direction <String>
 -ProtectionEntity <ASRProtectionEntity> [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRPObjectWithVMNetwork
```
Start-AzureSiteRecoveryTestFailoverJob -Network <ASRNetwork> [-NetworkType <String>]
 -RecoveryPlan <ASRRecoveryPlan> -Direction <String> [-WaitForCompletion] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByPEIdWithVMNetwork
```
Start-AzureSiteRecoveryTestFailoverJob -Network <ASRNetwork> [-NetworkType <String>] -Direction <String>
 -ProtectionEntityId <String> -ProtectionContainerId <String> [-WaitForCompletion] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByRPObject
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>]
 -RecoveryPlan <ASRRecoveryPlan> -Direction <String> [-WaitForCompletion] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByRPObjectWithLogicalNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>]
 -RecoveryPlan <ASRRecoveryPlan> -Direction <String> [-WaitForCompletion] -LogicalNetworkId <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRPObjectWithVMNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>]
 -RecoveryPlan <ASRRecoveryPlan> -Direction <String> [-WaitForCompletion] -VmNetworkId <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEIdWithLogicalNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>] -Direction <String>
 -ProtectionEntityId <String> -ProtectionContainerId <String> [-WaitForCompletion] -LogicalNetworkId <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEIdWithVMNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>] -Direction <String>
 -ProtectionEntityId <String> -ProtectionContainerId <String> [-WaitForCompletion] -VmNetworkId <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEObject
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>] -Direction <String>
 -ProtectionEntity <ASRProtectionEntity> [-WaitForCompletion] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEObjectWithLogicalNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>] -Direction <String>
 -ProtectionEntity <ASRProtectionEntity> [-WaitForCompletion] -LogicalNetworkId <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByPEObjectWithVMNetworkID
```
Start-AzureSiteRecoveryTestFailoverJob [-Network <ASRNetwork>] [-NetworkType <String>] -Direction <String>
 -ProtectionEntity <ASRProtectionEntity> [-WaitForCompletion] -VmNetworkId <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-AzureSiteRecoveryTestFailoverJob** cmdlet starts test failover of an Azure Site Recovery protection entity or recovery plan.
You can check whether the job succeeded by using the **Get-AzureRMSiteRecoveryJob** cmdlet.

## EXAMPLES

### Example 1: Start a test failover
```
PS C:\> $ProtectionContainer = Get-AzureSiteRecoveryProtectionContainer
PS C:\> $ProtectionEntity = Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer $ProtectionContainer
PS C:\> Start-AzureSiteRecoveryTestFailoverJob -ProtectionEntity $ProtectionEntity -Direction "PrimaryToRecovery"
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

The first command uses the **Get-AzureSiteRecoveryProtectionContainer** cmdlet to get a protected container, and then stores it in the $ProtectionContainer variable.

The second command gets the protected entities that belong to the protected container stored in $ProtectionContainer by using the **Get-AzureSiteRecoveryProtectionEntity** cmdlet.
The command stores the results in the $ProtectionEntity variable.

The final command starts the test failover operation for the protected entities stored in $ProtectionEntity and specifies the direction of the failover.

### Example 2: Start a test failover using a recovery plan
```
PS C:\> $RecoveryPlan = Get-AzureSiteRecoveryRecoveryPlan -Name "RecoveryPlan01"
Start-AzureSiteRecoveryTestFailoverJob -Direction PrimaryToRecovery -RecoveryPlan $RecoveryPlan
```

This command gets the recovery plan named RecoveryPlan01 for the current Azure Site Recovery vault by using the **Get-AzureSiteRecoveryRecoveryPlan** cmdlet.
The command stores the plan in the $RecoveryPlan variable.

The second command starts the test failover operation for the recovery plan stored in $RecoveryPlan and specifies the direction of the failover.

## PARAMETERS

### -Direction
Specifies the failover direction.
The acceptable values for this parameter are:

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

### -LogicalNetworkId
Specifies the ID of the logical network.

```yaml
Type: String
Parameter Sets: ByRPIdWithLogicalNetworkID, ByRPObjectWithLogicalNetworkID, ByPEIdWithLogicalNetworkID, ByPEObjectWithLogicalNetworkID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Network
Specifies the network object to use for test failover.
To obtain a network, use the **Get-AzureSiteRecoveryNetwork** cmdlet.

```yaml
Type: ASRNetwork
Parameter Sets: ByPEId, ByRPId, ByRPIdWithLogicalNetworkID, ByRPIdWithVMNetworkID, ByRPObject, ByRPObjectWithLogicalNetworkID, ByRPObjectWithVMNetworkID, ByPEIdWithLogicalNetworkID, ByPEIdWithVMNetworkID, ByPEObject, ByPEObjectWithLogicalNetworkID, ByPEObjectWithVMNetworkID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: ASRNetwork
Parameter Sets: ByRPIdWithVMNetwork, ByPEObjectWithVMNetwork, ByRPObjectWithVMNetwork, ByPEIdWithVMNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkType
Specifies the network type to use for test failover.
The acceptable values for this parameter are:

- None
- New
- Existing

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
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### -ProtectionContainerId
Specifies the ID of a protected container.
This cmdlet starts the job for a protected virtual machine that belongs to the container that this cmdlet specifies.

```yaml
Type: String
Parameter Sets: ByPEId, ByPEIdWithVMNetwork, ByPEIdWithLogicalNetworkID, ByPEIdWithVMNetworkID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionEntity
Specifies the Site Recovery protection entity object.

```yaml
Type: ASRProtectionEntity
Parameter Sets: ByPEObjectWithVMNetwork, ByPEObjectWithLogicalNetworkID, ByPEObjectWithVMNetworkID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: ASRProtectionEntity
Parameter Sets: ByPEObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionEntityId
Specifies the ID of a protected virtual machine for which to start the job.

```yaml
Type: String
Parameter Sets: ByPEId, ByPEIdWithVMNetwork, ByPEIdWithLogicalNetworkID, ByPEIdWithVMNetworkID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPlan
Specifies a recovery plan for which to start the job.

```yaml
Type: ASRRecoveryPlan
Parameter Sets: ByRPObjectWithVMNetwork, ByRPObjectWithLogicalNetworkID, ByRPObjectWithVMNetworkID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: ASRRecoveryPlan
Parameter Sets: ByRPObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RpId
Specifies the ID of a recovery plan for which to start the job.

```yaml
Type: String
Parameter Sets: ByRPId, ByRPIdWithLogicalNetworkID, ByRPIdWithVMNetworkID, ByRPIdWithVMNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmNetworkId
Specifies the ID of the virtual machine network.

```yaml
Type: String
Parameter Sets: ByRPIdWithVMNetworkID, ByRPObjectWithVMNetworkID, ByPEIdWithVMNetworkID, ByPEObjectWithVMNetworkID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForCompletion
Indicates that the cmdlet waits for the operation to complete before it returns control to the Windows PowerShell console.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSiteRecoveryProtectionContainer](./Get-AzureSiteRecoveryProtectionContainer.md)

[Get-AzureSiteRecoveryNetwork](./Get-AzureSiteRecoveryNetwork.md)

[Get-AzureSiteRecoveryProtectionEntity](./Get-AzureSiteRecoveryProtectionEntity.md)

[Get-AzureSiteRecoveryRecoveryPlan](./Get-AzureSiteRecoveryRecoveryPlan.md)

[Start-AzureSiteRecoveryUnplannedFailoverJob](./Start-AzureSiteRecoveryUnplannedFailoverJob.md)


