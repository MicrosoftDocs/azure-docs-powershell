---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: .\Get-AzureSiteRecoveryRecoveryPlan.md
schema: 2.0.0
---

# Get-AzureSiteRecoveryRecoveryPlanFile

## SYNOPSIS
Downloads an Azure Site Recovery plan in XML format.

## SYNTAX

### ByRPObject (Default)
```
Get-AzureSiteRecoveryRecoveryPlanFile -Path <String> -RecoveryPlan <ASRRecoveryPlan> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### ById
```
Get-AzureSiteRecoveryRecoveryPlanFile -Path <String> -Id <String> [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryRecoveryPlanFile** cmdlet downloads an Azure Site Recovery plan in XML format.
You can use this file to update the recovery plan and then upload it to the Microsoft Azure Site Recovery server.

A recovery plan gathers virtual machines in a group for the purposes of failover and recovery.

## EXAMPLES

### Example 1: Get a recovery plan file
```
PS C:\>$RecoveryPlan = Get-AzureSiteRecoveryRecoveryPlan 
PS C:\> Get-AzureSiteRecoveryRecoveryPlanFile -RecoveryPlan $RecoveryPlan -Path "C:\Users\Contoso\Desktop\RecoveryPlan.xml"
```

This command uses the **Get-AzureSiteRecoveryRecoveryPlan** cmdlet to get the recovery plan, and then stores it in the $RecoveryPlan variable.

The second command uses the **GetAzureSiteRecoveryRecoveryPlanFile** cmdlet to get the site recovery plan XML file stored in $RecoveryPlan.
The command stores the XML file at the specified path.

## PARAMETERS

### -Id
Specifies the ID of the recovery plan to get.

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

### -Path
Specifies the full path to store the recovery plan XML file.

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

### -RecoveryPlan
Specifies an **ASRRecoveryPlan** object from which to get the recovery plan.
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

