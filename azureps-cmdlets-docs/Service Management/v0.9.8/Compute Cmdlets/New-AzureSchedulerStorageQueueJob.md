---
external help file: SMAzure_Compute.xml
online version: 29c40d46-86c3-4f67-94f7-484371fdfba5
schema: 2.0.0
---

# New-AzureSchedulerStorageQueueJob
## SYNOPSIS
Creates a scheduler job that has a Storage action.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureSchedulerStorageQueueJob [-EndTime <DateTime>] [-ErrorActionHeaders <Hashtable>]
 [-ErrorActionMethod <String>] [-ErrorActionQueueMessageBody <String>] [-ErrorActionRequestBody <String>]
 [-ErrorActionSASToken <String>] [-ErrorActionStorageAccount <String>] [-ErrorActionStorageQueue <String>]
 [-ErrorActionURI <Uri>] [-ExecutionCount <Int32>] [-Frequency <String>] [-Interval <Int32>]
 [-JobState <String>] [-StartTime <DateTime>] [-StorageQueueMessage <String>] -JobCollectionName <String>
 -JobName <String> -Location <String> -SASToken <String> -StorageQueueAccount <String>
 -StorageQueueName <String>
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureSchedulerStorageQueueJob [-EndTime <DateTime>] [-ErrorActionHeaders <Hashtable>]
 [-ExecutionCount <Int32>] [-Frequency <String>] [-Interval <Int32>] [-JobState <String>]
 [-StorageQueueMessage <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The New-AzureSchedulerStorageQueueJob cmdlet creates a scheduler job that has an Azure Storage action.

## EXAMPLES

### Example 1: Create a Storage job that runs once
```
PS C:\>New-AzureSchedulerStorageQueueJob -JobCollectionName "JobCollection01" -JobName "Job01" -Location "North Central US" -StorageQueueAccount "ContosoStorageAccount" -StorageQueueName "ContosoStorageQueue" -SASToken "?sv=2012-02-12&si=samplePolicy%2F30%2F2014%206%3A37%3A36%20PM&sig=vLQEbSfZbTFh7q3YrzlxBeL%2BjiYKp0gE6lMJ0a5Nb4M%3D"
```

This command creates a scheduler Storage job as part of the collection named JobCollection01.
The command specifies the Storage account, queue name, and SAS token.
The job runs once, immediately.

### Example 2: Create a Storage job that runs a specified number of times
```
PS C:\>New-AzureSchedulerStorageQueueJob -JobCollectionName "JobCollection01" -JobName "Job12" -Location "North Central US"-StorageQueueAccount "ContosoStorageAccount" -StorageQueueName "ContosoStorageQueue" -SASToken "?sv=2012-02-12&si=samplePolicy%2F30%2F2014%206%3A37%3A36%20PM&sig=vLQEbSfZbTFh7q3YrzlxBeL%2BjiYKp0gE6lMJ0a5Nb4M%3D" -ExecutionCount 20 -Frequency "Hour" -Interval 2
```

This command creates a scheduler Storage job as part of the collection named JobCollection01.
The command specifies the Storage account, queue name, and SAS token.
The job runs 20 times in total, twice every hour.

## PARAMETERS

### -EndTime
Specifies a time, as a DateTime object, for the scheduler to stop initiating the job.
To obtain a DateTime object, use the Get-Date cmdlet.
For more information, type Get-Help Get-Date.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorActionHeaders
Specifies headers as a hash table.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorActionMethod
Specifies the method for HTTP and HTTPS action types.
Valid values are: 

-- GET
-- PUT
-- POST
-- HEAD
-- DELETE

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorActionQueueMessageBody
Specifies the body for Storage job actions.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorActionRequestBody
Specifies the body for PUT and POST job actions.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorActionSASToken
Specifies the Shared Access Signature (SAS) token for the Storage queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorActionStorageAccount
Specifies the name of the Storage account.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorActionStorageQueue
Specifies the name of the Storage queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorActionURI
Specifies the URI for the error job action.

```yaml
Type: Uri
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExecutionCount
Specifies the number occurrences of a job that run.
By default, a job recurs indefinitely.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Frequency
Specifies the maximum frequency for this scheduler job.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interval
Specifies the interval of recurrence at the frequency specified by using the Frequency parameter.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCollectionName
Specifies the name of the collection to contain the scheduler job.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobName
Specifies the name for the scheduler job.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobState
Specifies the state for the scheduler job.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -SASToken
Specifies the SAS token for the Storage queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Specifies a time, as a DateTime object, for the job to start.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQueueAccount
Specifies the Storage account name.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageQueueMessage
Specifies the queue message for Storage job.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQueueName
Specifies the name of the Storage queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureSchedulerStorageQueueJob](29c40d46-86c3-4f67-94f7-484371fdfba5)

