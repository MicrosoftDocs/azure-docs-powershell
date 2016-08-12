---
external help file: SMAzure_Compute.xml
online version: 23b849a7-7403-491a-9d21-2104137052ec
schema: 2.0.0
---

# New-AzureSchedulerHttpJob
## SYNOPSIS
Creates a scheduler job that has an HTTP action.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureSchedulerHttpJob [-ClientCertificatePassword <String>] [-ClientCertificatePfx <Object>]
 [-ErrorActionHeaders <Hashtable>] [-Headers <Hashtable>] [-JobState <String>] -HttpAuthenticationType <String>
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureSchedulerHttpJob [-ClientCertificatePassword <String>] [-ClientCertificatePfx <Object>]
 [-EndTime <DateTime>] [-ErrorActionHeaders <Hashtable>] [-ErrorActionMethod <String>]
 [-ErrorActionQueueMessageBody <String>] [-ErrorActionRequestBody <String>] [-ErrorActionSASToken <String>]
 [-ErrorActionStorageAccount <String>] [-ErrorActionStorageQueue <String>] [-ErrorActionURI <Uri>]
 [-ExecutionCount <Int32>] [-Frequency <String>] [-Headers <Hashtable>] [-HttpAuthenticationType <String>]
 [-Interval <Int32>] [-JobState <String>] [-RequestBody <String>] [-StartTime <DateTime>]
 -JobCollectionName <String> -JobName <String> -Location <String> -Method <String> -URI <Uri>
```

### UNNAMED_PARAMETER_SET_3
```
New-AzureSchedulerHttpJob [-EndTime <DateTime>] [-ErrorActionHeaders <Hashtable>] [-ExecutionCount <Int32>]
 [-Frequency <String>] [-Headers <Hashtable>] [-Interval <Int32>] [-JobState <String>]
```

### UNNAMED_PARAMETER_SET_4
```
New-AzureSchedulerHttpJob [-ErrorActionHeaders <Hashtable>] [-Headers <Hashtable>] [-JobState <String>]
 [-RequestBody <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The New-AzureSchedulerHttpJob cmdlet creates a scheduler job that has an HTTP action.

## EXAMPLES

### Example 1: Create an HTTP job
```
PS C:\>New-AzureSchedulerHttpJob -JobCollectionName "JobCollection01" -JobName "Job01" -Location "North Central US" -Method "GET" -URI http://www.contoso.com
```

This command creates a scheduler HTTP job in the job collection named JobCollection01.
The command specifies a URI and specifies GET as the method.

### Example 2: Create an HTTP job for a specific run count
```
PS C:\>New-AzureSchedulerHttpJob -JobCollectionName "JobCollection01 -JobName "Job23" -Location "North Central US" -Method "GET" -URI http://www.contoso.com -ExecutionCount 20
```

This command creates scheduler http job in the job collection named JobCollection01.
The command specifies a URI and specifies GET as the method.
This command causes the job to run 20 times.

## PARAMETERS

### -ClientCertificatePassword
@{Text=}

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientCertificatePfx
@{Text=}

```yaml
Type: Object
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies a time, as a DateTime object, for the scheduler to stop initiating jobs.
To obtain a DateTime object, use the Get-Date cmdlet.
For more information, type Get-Help Get-Date.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorActionHeaders
Specifies headers as a hashtable.

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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorActionQueueMessageBody
Specifies the body for storage job actions.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorActionSASToken
Specifies the Shared Access Signature (SAS) token for the storage queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorActionStorageAccount
Specifies the name of the storage account.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorActionStorageQueue
Specifies the name of the storage queue.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Headers
Specifies the headers as a hashtable.

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

### -HttpAuthenticationType
@{Text=}

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

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Method
Specifies the method for HTTP and HTTPS action types.
Valid values are: 

-- GET
-- PUT
-- POST
-- HEAD
-- DELETE

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestBody
Specifies the body for PUT and POST job actions.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies a time, as a DateTime object, for the job to start.

```yaml
Type: DateTime
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -URI
Specifies a URI for a job action.

```yaml
Type: Uri
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureSchedulerHttpJob](23b849a7-7403-491a-9d21-2104137052ec)

