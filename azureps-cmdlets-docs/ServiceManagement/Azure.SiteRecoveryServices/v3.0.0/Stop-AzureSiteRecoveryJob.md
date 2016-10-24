---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: b2ac1af1-924e-4839-a7f1-10815402e801
schema: 2.0.0
ms.assetid: 1DA46338-273E-4C73-AFB7-BC25E9FB83DD
---

# Stop-AzureSiteRecoveryJob

## SYNOPSIS
Stops a Site Recovery job.

## SYNTAX

### ByObject (Default)
```
Stop-AzureSiteRecoveryJob -Job <ASRJob> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ById
```
Stop-AzureSiteRecoveryJob -Id <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AzureSiteRecoveryJob** cmdlet stops an Azure Site Recovery job.

## EXAMPLES

### Example 1: Stop all jobs
```
PS C:\>$Jobs = Get-AzureSiteRecoveryJob 
PS C:\> Stop-AzureSiteRecoveryJob -Job $Jobs
```

The first command gets the Azure Site Recovery jobs for the current Azure Site Recovery vault by using the Get-AzureSiteRecoveryJob cmdlet, and then stores the results in the $Jobs variable.

The second command stops the jobs specified by $Jobs.

## PARAMETERS

### -Id
Specifies the ID of the job to stop.

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

### -Job
Specifies the job to stop.

```yaml
Type: ASRJob
Parameter Sets: ByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSiteRecoveryJob](./Get-AzureSiteRecoveryJob.md)

[Restart-AzureSiteRecoveryJob](./Restart-AzureSiteRecoveryJob.md)

[Resume-AzureSiteRecoveryJob](./Resume-AzureSiteRecoveryJob.md)


