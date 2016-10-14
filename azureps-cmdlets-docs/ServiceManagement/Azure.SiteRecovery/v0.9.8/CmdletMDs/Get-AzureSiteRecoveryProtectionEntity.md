---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: .\Set-AzureSiteRecoveryProtectionEntity.md
schema: 2.0.0
---

# Get-AzureSiteRecoveryProtectionEntity

## SYNOPSIS
Gets protected objects in Azure Site Recovery.

## SYNTAX

### ByObject (Default)
```
Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer <ASRProtectionContainer> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### ByObjectWithId
```
Get-AzureSiteRecoveryProtectionEntity -Id <String> -ProtectionContainer <ASRProtectionContainer>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByIDsWithId
```
Get-AzureSiteRecoveryProtectionEntity -Id <String> -ProtectionContainerId <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### ByIDsWithName
```
Get-AzureSiteRecoveryProtectionEntity -Name <String> -ProtectionContainerId <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### ByObjectWithName
```
Get-AzureSiteRecoveryProtectionEntity -Name <String> -ProtectionContainer <ASRProtectionContainer>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByIDs
```
Get-AzureSiteRecoveryProtectionEntity -ProtectionContainerId <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryProtectionEntity** cmdlet gets protected objects in Microsoft Azure Site Recovery, such as virtual machines.

## EXAMPLES

### Example 1: Display a protected virtual machine in a container
```
PS C:\>$Container = Get-AzureSiteRecoveryProtectionContainer
PS C:\> Get-AzureSiteRecoveryProtectionEntity -ProtectionContainer $Container 
ID                           : 43aaab46-1cb0-4c39-8077-9a091c3b05ce
ServerId                     : 4a94c4a9-c856-4577-afbd-367fe9b3ce9c
ProtectionContainerId        : 4a94c4a9-c856-4577-afbd-367fe9b3ce9c_1c513d45-645d-4ed0-b9ae-e7b869a1f7fc
Name                         : testvm
Type                         : VirtualMachine
FabricObjectId               : 506B3CAC-5758-49E2-98C4-E5B0512E4D8E
Protected                    : False
CanCommit                    : False
CanFailover                  : False
CanReverseReplicate          : False
ActiveLocation               : Primary
ProtectionStateDescription   : Enabling protection
ReplicationHealth            : 
TestFailoverStateDescription : Nonev
ReplicationProvider          : HyperVReplica
```

The first command gets a protected container by using the **Get-AzureSiteRecoveryProtectionContainer** cmdlet, and then stores that object in the $Container variable.

The second command gets the protected virtual machine that belongs to the container stored in $Container, and then displays it.

## PARAMETERS

### -Id
Specifies the ID of a protection entity to get.

```yaml
Type: String
Parameter Sets: ByObjectWithId, ByIDsWithId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a protected virtual machine to get.

```yaml
Type: String
Parameter Sets: ByIDsWithName, ByObjectWithName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionContainer
Specifies an **ASRProtectionContainer** object.
To obtain an **ASRProtectionContainer** object, use the **Get-AzureSiteRecoveryProtectionContainer** cmdlet.
This cmdlet gets objects in the container that this parameter specifies.

```yaml
Type: ASRProtectionContainer
Parameter Sets: ByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: ASRProtectionContainer
Parameter Sets: ByObjectWithId, ByObjectWithName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionContainerId
Specifies the ID of a protected container.
This cmdlet gets objects in the container that this parameter specifies.

```yaml
Type: String
Parameter Sets: ByIDsWithId, ByIDsWithName, ByIDs
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

[Set-AzureSiteRecoveryProtectionEntity](.\Set-AzureSiteRecoveryProtectionEntity.md)

[Get-AzureSiteRecoveryProtectionContainer](.\Get-AzureSiteRecoveryProtectionContainer.md)

