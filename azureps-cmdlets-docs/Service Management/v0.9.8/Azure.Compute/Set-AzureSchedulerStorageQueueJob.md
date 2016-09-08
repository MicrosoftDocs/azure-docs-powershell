---
external help file: SMAzure_Compute.xml
online version: bb736406-8b48-4bdf-b67b-0c928e674c7d
schema: 2.0.0
---

# Set-AzureSchedulerStorageQueueJob
## SYNOPSIS
Updates a scheduler job that has a storage action.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-AzureSchedulerStorageQueueJob [-Location] <String> [[-Interval] <Int32>] [[-Frequency] <String>]
 [[-EndTime] <DateTime>] [[-ExecutionCount] <Int32>] [[-JobState] <String>] [[-ErrorActionMethod] <String>]
 [[-ErrorActionURI] <Uri>] [[-ErrorActionRequestBody] <String>] [[-ErrorActionHeaders] <Hashtable>]
 [[-ErrorActionStorageAccount] <String>] [-JobCollectionName] <String> [[-ErrorActionStorageQueue] <String>]
 [[-ErrorActionSASToken] <String>] [[-ErrorActionQueueMessageBody] <String>] [-JobName] <String>
 [[-StorageQueueAccount] <String>] [[-StorageQueueName] <String>] [[-SASToken] <String>]
 [[-StorageQueueMessage] <String>] [[-StartTime] <DateTime>] [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Set-AzureSchedulerStorageQueueJob [[-Interval] <Int32>] [[-Frequency] <String>] [[-EndTime] <DateTime>]
 [[-ExecutionCount] <Int32>] [[-JobState] <String>] [[-ErrorActionHeaders] <Hashtable>] [-PassThru]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Set-AzureSchedulerStorageQueueJob cmdlet updates a scheduler job that has an Azure Storage action.

## EXAMPLES

### Example 1: Update a Storage queue message
```
PS C:\>Set-AzureSchedulerStorageQueueJob -Location "North Central US" -JobCollectionName "JobCollection01 -JobName "Job12" -StorageQueueMessage "Updated message"
```

This command updates the queue message for the Storage job named Job12.
The command specifies the job collection name and the location.

### Example 2: Enable a Storage queue job
```
PS C:\>Set-AzureSchedulerStorageQueueJob -Location "North Central US" -JobCollectionName "JobCollection02" -JobName "Job16" -JobState "Enabled"
```

This command enables the job named Job16.
The command changes the state of the job to Enabled by specifying that value for the JobState parameter.

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
Position: 12
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
Position: 18
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
Position: 15
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
Position: 22
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
Position: 17
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
Position: 21
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
Position: 19
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
Position: 20
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
Position: 16
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
Position: 13
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
Position: 11
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
Position: 10
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
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobName
Specifies the name of the scheduler job to update.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 3
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
Position: 14
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
Position: 1
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns an object representing the item on which it operates.
By default, this cmdlet does not generate any output.

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

### -SASToken
Specifies the SAS token for the Storage queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 6
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
Position: 9
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

Required: False
Position: 4
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageQueueMessage
Specifies the queue message for the Storage job.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 7
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

Required: False
Position: 5
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureSchedulerStorageQueueJob](bb736406-8b48-4bdf-b67b-0c928e674c7d)

