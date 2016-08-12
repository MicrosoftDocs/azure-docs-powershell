---
external help file: SMAzure_Compute.xml
online version: aaed4c39-d209-4663-b058-b480553ee6a9
schema: 2.0.0
---

# Remove-AzureSchedulerJob
## SYNOPSIS
Deletes a scheduler job.

## SYNTAX

```
Remove-AzureSchedulerJob [[-Location] <String>] [-JobCollectionName] <String> [-JobName] <String> [-Force]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Remove-AzureSchedulerJob cmdlet deletes a scheduler job.

## EXAMPLES

### Example 1: Delete a scheduler job
```
PS C:\>Remove-AzureSchedulerJob -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job17"
```

This command deletes the job named Job17.
That job is part of the job collection named JobCollection01 and is in of the specified location.

## PARAMETERS

### -Force
Indicates that this cmdlet removes the scheduler job without prompting you for confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCollectionName
Specifies the name of the collection that contains the scheduler job to delete.

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
Specifies the name of a scheduler job to delete.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSchedulerJob](aaed4c39-d209-4663-b058-b480553ee6a9)

