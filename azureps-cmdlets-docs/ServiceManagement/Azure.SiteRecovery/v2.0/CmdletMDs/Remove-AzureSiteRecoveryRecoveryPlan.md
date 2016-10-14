---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\Get-AzureSiteRecoveryRecoveryPlan.md
schema: 2.0.0
---

# Remove-AzureSiteRecoveryRecoveryPlan

## SYNOPSIS
Removes a recovery plan from an Azure Site Recovery vault.

## SYNTAX

### ByRPObject (Default)
```
Remove-AzureSiteRecoveryRecoveryPlan -RecoveryPlan <ASRRecoveryPlan> [-WaitForCompletion] [-Force]
 [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Remove-AzureSiteRecoveryRecoveryPlan -Id <String> [-WaitForCompletion] [-Force] [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureSiteRecoveryRecoveryPlan** cmdlet removes a recovery plan from the current Microsoft Azure Site Recovery vault.

## EXAMPLES

### Example 1: Remove a recovery plan
```
PS C:\>$RecoveryPlan = Get-AzureSiteRecoveryRecoveryPlan 
PS C:\> Remove-AzureSiteRecoveryRecoveryPlan -RecoveryPlan $RecoveryPlan
ID               : 20329f92-9ed6-4529-8b74-d83309623248
ClientRequestId  : 6c967844-096f-4ca6-a166-55936fd6d61c-2014-36-06 15:36:40Z-P
State            : NotStarted
StateDescription : NotStarted
StartTime        : 
EndTime          : 
AllowedActions   : {}
Name             : 
Tasks            : {}
Errors           : {}
```

The first command uses the **Get-AzureSiteRecoveryRecoveryPlan** cmdlet to get the Azure Site Recovery plan, and then stores it in the $RecoveryPlan variable.

The second command uses **Remove-AzureSiteRecoveryRecoveryPlan** to remove the recovery plan contained in $RecoveryPlan.

## PARAMETERS

### -Force
Indicates that this cmdlet does not prompt you for confirmation.

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

### -Id
Specifies the ID of the recovery plan to remove.

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

### -RecoveryPlan
Specifies an **ASRRecoveryPlan** object to remove.
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

[New-AzureSiteRecoveryRecoveryPlan](.\New-AzureSiteRecoveryRecoveryPlan.md)

[Update-AzureSiteRecoveryRecoveryPlan](.\Update-AzureSiteRecoveryRecoveryPlan.md)

