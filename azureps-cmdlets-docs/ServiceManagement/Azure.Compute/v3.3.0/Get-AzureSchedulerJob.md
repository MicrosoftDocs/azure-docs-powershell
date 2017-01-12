---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 8EED9813-5106-4D6C-B869-97BCBD7845AC
online version: 
schema: 2.0.0
---

# Get-AzureSchedulerJob

## SYNOPSIS
Gets a list of scheduler jobs or a particular scheduler job.

## SYNTAX

```
Get-AzureSchedulerJob [-Location] <String> [-JobCollectionName] <String> [[-JobName] <String>]
 [[-JobState] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type `(Get-Module -Name Azure).Version`.

The **Get-AzureSchedulerJobCollection** cmdlet gets a list of scheduler jobs or a particular scheduler job.

## EXAMPLES

### Example 1: Get all jobs in a collection
```
PS C:\> Get-AzureSchedulerJob -Location "North Central US" -JobCollectionName "JobCollection01"
```

This command gets scheduler jobs that are part of the job collection named JobCollection01.

### Example 2: Get a named job
```
PS C:\> Get-AzureSchedulerJob -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job01"
```

This command gets the job named Job01 from the collection named JobCollection01 in the specified location.

### Example 3: Get disabled jobs in a collection
```
PS C:\> Get-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01" -JobState "Disabled"
```

This command gets all disabled scheduler jobs that are part of JobCollection01 in the specified location.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCollectionName
Specifies the name of the collection that contains the scheduler job to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobName
Specifies the name of a scheduler job to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobState
Specifies the state of scheduler jobs to get.
The acceptable values for this parameter are:

- Enabled
- Disabled
- Faulted
- Completed

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the name of the location that hosts the cloud service.
The acceptable values for this parameter are:

- Anywhere Asia
- Anywhere Europe
- Anywhere US
- East Asia
- East US
- North Central US
- North Europe
- South Central US
- Southeast Asia
- West Europe
- West US

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Remove-AzureSchedulerJob](./Remove-AzureSchedulerJob.md)


