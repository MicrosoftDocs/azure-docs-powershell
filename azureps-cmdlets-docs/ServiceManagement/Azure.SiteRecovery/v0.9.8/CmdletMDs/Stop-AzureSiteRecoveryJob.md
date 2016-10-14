---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: .\Get-AzureSiteRecoveryJob.md
schema: 2.0.0
---

# Stop-AzureSiteRecoveryJob

## SYNOPSIS
Stops an Azure Site Recovery job.

## SYNTAX

### ByObject (Default)
```
Stop-AzureSiteRecoveryJob -Job <ASRJob> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ById
```
Stop-AzureSiteRecoveryJob -Id <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-AzureSiteRecoveryJob** cmdlet stops a Microsoft Azure Site Recovery job.
Use this cmdlet for running jobs only.
To see which actions you can take on a job, look at the **AllowedActions** property of the job object.

## EXAMPLES

### Example 1: Stop all jobs
```
PS C:\>$Jobs= Get-AzureSiteRecoveryJob 
PS C:\> Stop-AzureSiteRecoveryJob -Job $Jobs
```

The first command gets the Azure Site Recovery jobs for the current Azure Site Recovery vault by using the **Get-AzureSiteRecoveryJob** cmdlet, and then stores the results in the $Jobs variable.

The second command stops the jobs specified by $Jobs.

## PARAMETERS

### -Id
Specifies the ID of a job to stop.

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
Specifies an Azure Site Recovery job object to stop.
To obtain a job object, use the **Get-AzureSiteRecoveryJob** cmdlet.

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

[Get-AzureSiteRecoveryJob](.\Get-AzureSiteRecoveryJob.md)

[Restart-AzureSiteRecoveryJob](.\Restart-AzureSiteRecoveryJob.md)

[Resume-AzureSiteRecoveryJob](.\Resume-AzureSiteRecoveryJob.md)

