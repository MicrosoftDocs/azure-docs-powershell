---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\New-AzureSiteRecoveryRecoveryPlan.md
schema: 2.0.0
---

# Get-AzureSiteRecoveryRecoveryPlan

## SYNOPSIS
Gets information about an Azure Site Recovery plan.

## SYNTAX

### Default (Default)
```
Get-AzureSiteRecoveryRecoveryPlan [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ById
```
Get-AzureSiteRecoveryRecoveryPlan -Id <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByName
```
Get-AzureSiteRecoveryRecoveryPlan -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryRecoveryPlan** cmdlet gets information about the recovery plan for the current Microsoft Azure Site Recovery vault.

A recovery plan gathers virtual machines in a group for the purposes of failover and recovery.

## EXAMPLES

### Example 1: Get a recovery plan
```
PS C:\>Get-AzureSiteRecoveryRecoveryPlan
ID                            Name                          ServerId                      TargetServerId
--                            ----                          --------                      --------------
71de8ebc-1e9a-4242-aec3-ee... ContosoPlan                   4a94c4a9-c856-4577-afbd-36... 78facf56-b273-4941-82fd-cc...
```

This command gets information about the recovery plan for the current Azure Site Recovery vault.

## PARAMETERS

### -Id
Specifies the ID of the recovery plan about which to get information.

```yaml
Type: String
Parameter Sets: ById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the recovery plan about which to get information.

```yaml
Type: String
Parameter Sets: ByName
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

[New-AzureSiteRecoveryRecoveryPlan](.\New-AzureSiteRecoveryRecoveryPlan.md)

[Remove-AzureSiteRecoveryRecoveryPlan](.\Remove-AzureSiteRecoveryRecoveryPlan.md)

[Update-AzureSiteRecoveryRecoveryPlan](.\Update-AzureSiteRecoveryRecoveryPlan.md)

