---
external help file: SMAzure_Compute.xml
online version: aaed4c39-d209-4663-b058-b480553ee6a9
schema: 2.0.0
---

# Get-AzureSchedulerJobHistory
## SYNOPSIS
Gets history for a scheduler job.

## SYNTAX

```
Get-AzureSchedulerJobHistory [-Location] <String> [-JobCollectionName] <String> [-JobName] <String>
 [[-JobStatus] <String>] [-First] [-Skip] [-IncludeTotalCount]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Get-AzureSchedulerJobHistory cmdlet gets the history for a scheduler job.

## EXAMPLES

### Example 1: Get history for a job by using its name
```
PS C:\>Get-AzureSchedulerJobHistory -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job01"
```

This command gets the history of the job named Job01.
That job belongs to the job collection named JobCollection01 in the specified location.

### Example 2: Get history for a failed job by using its name
```
PS C:\>Get-AzureSchedulerJobHistory -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job12" -JobStatus "Failed"
```

This command gets the history of the job named Job12 that has a status of Failed.
That job belongs to the job collection named JobCollection01 in the specified location.

## PARAMETERS

### -JobCollectionName
Specifies the name of a scheduler job collection.
This cmdlet gets the history for a job that belongs to the collection that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobName
Specifies the name of a scheduler job for which to get the history.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobStatus
Specifies the status of scheduler job for which to get the history.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the name of the location that hosts the cloud service.
Valid values are: 

-- Anywhere Asia
-- Anywhere Europe
-- Anywhere US
-- East Asia
-- East US
-- North Central US
-- North Europe
-- South Central US
-- Southeast Asia
-- West Europe
-- West US

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -First
Gets only the specified number of objects.
Enter the number of objects to get.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Skip
Ignores the specified number of objects and then gets the remaining objects.
Enter the number of objects to skip.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeTotalCount
Reports the total number of objects in the data set (an integer) followed by the selected objects.
If the cmdlet cannot determine the total count, it displays "Unknown total count." The integer has an Accuracy property that indicates the reliability of the total count value.
The value of Accuracy ranges from 0.0 to 1.0 where 0.0 means that the cmdlet could not count the objects, 1.0 means that the count is exact, and a value between 0.0 and 1.0 indicates an increasingly reliable estimate.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSchedulerJob](aaed4c39-d209-4663-b058-b480553ee6a9)

[Get-AzureSchedulerJobCollection](1f6e64a2-021e-4ad7-93a4-9e1138607f01)

