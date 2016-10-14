---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: .\Get-AzureSiteRecoveryRecoveryPlan.md
schema: 2.0.0
---

# New-AzureSiteRecoveryRecoveryPlan

## SYNOPSIS
Adds a recovery plan to an Azure Site Recovery vault.

## SYNTAX

```
New-AzureSiteRecoveryRecoveryPlan -File <String> [-WaitForCompletion] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSiteRecoveryRecoveryPlan** cmdlet adds a recovery plan to a Microsoft Azure Site Recovery vault.

A recovery plan gathers virtual machines in a group for the purposes of failover and recovery.

## EXAMPLES

### Example 1: Add a recovery plan to an Azure Site Recovery vault
```
PS C:\>New-AzureSiteRecoveryRecoveryPlan -File "C:\Users\Contoso\Desktop\RecoveryPlan.xml"
ID               : 189283c7-7fd9-4010-8bf1-d2a2e4a46df4
ClientRequestId  : 6c56d96e-dfdd-4898-81cf-8562f51a8129-2014-34-06 15:34:23Z-P
State            : NotStarted
StateDescription : NotStarted
StartTime        : 
EndTime          : 
AllowedActions   : {}
Name             : 
Tasks            : {}
Errors           : {}
```

This command adds the recovery plan named RecoveryPlan.xml to the Azure Site Recovery vault.

## PARAMETERS

### -File
Specifies the complete path to the recovery plan XML file.

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

[Get-AzureSiteRecoveryRecoveryPlan](.\Get-AzureSiteRecoveryRecoveryPlan.md)

[Remove-AzureSiteRecoveryRecoveryPlan](.\Remove-AzureSiteRecoveryRecoveryPlan.md)

[Update-AzureSiteRecoveryRecoveryPlan](.\Update-AzureSiteRecoveryRecoveryPlan.md)

