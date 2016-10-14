---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: .\Restart-AzureSiteRecoveryJob.md
schema: 2.0.0
---

# Get-AzureSiteRecoveryJob

## SYNOPSIS
Gets Azure Site Recovery jobs.

## SYNTAX

### ByParam (Default)
```
Get-AzureSiteRecoveryJob [-StartTime <DateTime>] [-EndTime <DateTime>] [-TargetObjectId <String>]
 [-State <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ById
```
Get-AzureSiteRecoveryJob -Id <String> [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByObject
```
Get-AzureSiteRecoveryJob -Job <ASRJob> [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryJob** cmdlet gets Microsoft Azure Site Recovery jobs.
You can use this cmdlet to view the information of the operation for current Azure Site Recovery vault.

## EXAMPLES

### Example 1: Get a job by specifying an ID
```
PS C:\>Get-AzureSiteRecoveryJob -Id "033785cc-9f72-4f07-8e78-e4d1e942a7ae" 
Name             : SaveRecoveryPlan
ID               : 033785cc-9f72-4f07-8e78-e4d1e942a7ae
ClientRequestId  : d604206b-32e1-4d5b-9a23-32b118d14a1e-2015-02-20 07:20:42Z-P
State            : Succeeded
StateDescription : Completed
StartTime        : 20-02-2015 07:20:45 +05:30
EndTime          : 20-02-2015 07:20:46 +05:30
TargetObjectId   : cfb445bf-fd14-4b5d-b9ac-5154e1415ef2
TargetObjectType : RecoveryPlan
TargetObjectName : RP
AllowedActions   : {Cancel}
Tasks            : {Save a recovery plan task}
Errors           : {}
```

This command gets the Azure Site Recovery job that has the specified ID.

### Example 2: Gets a job based on time
```
PS C:\>Get-AzureSiteRecoveryJob -StartTime "20-02-2015 01:00:00" -EndTime "21-02-2015 01:00:00"
Name             : SaveRecoveryPlan
ID               : 033785cc-9f72-4f07-8e78-e4d1e942a7ae
ClientRequestId  : d604206b-32e1-4d5b-9a23-32b118d14a1e-2015-02-20 07:20:42Z-P
State            : Succeeded
StateDescription : Completed
StartTime        : 20-02-2015 07:20:45 +05:30
EndTime          : 20-02-2015 07:20:46 +05:30
TargetObjectId   : cfb445bf-fd14-4b5d-b9ac-5154e1415ef2
TargetObjectType : RecoveryPlan
TargetObjectName : RP
AllowedActions   : {Cancel}
Tasks            : {Save a recovery plan task}
Errors           : {}
```

This command gets Azure Site Recovery jobs that fall between the specified start time and end time.

## PARAMETERS

### -EndTime
Specifies an end time as a **DateTime** object.
This cmdlet gets jobs that begin before the time that this parameter specifies.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of a job to get.

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
Specifies an Azure Site Recovery job object to get.

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

### -StartTime
Specifies a start time as a **DateTime** object.
This cmdlet gets jobs that begin after the time that this parameter specifies.
To obtain a **DateTime** object, use the **Get-Date** cmdlet.
For more information, type `Get-Help Get-Date`.

```yaml
Type: DateTime
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Specifies an input state for an Azure Site Recovery job.
This cmdlet gets jobs that match the state that this parameter specifies.
Valid values are: 

- NotStarted 
- InProgress
- Succeeded
- Other
- Failed
- Cancelled 
- Suspended

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetObjectId
Specifies the ID of the object to which the recovery job is targeted.

```yaml
Type: String
Parameter Sets: ByParam
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

[Restart-AzureSiteRecoveryJob](.\Restart-AzureSiteRecoveryJob.md)

[Resume-AzureSiteRecoveryJob](.\Resume-AzureSiteRecoveryJob.md)

[Stop-AzureSiteRecoveryJob](.\Stop-AzureSiteRecoveryJob.md)

