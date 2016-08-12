---
external help file: RMAzure_Storage.xml
online version: 606cb5d3-e7fd-4647-b980-329334abc795
schema: 2.0.0
---

# Get-AzureStorageBlobCopyState
## SYNOPSIS
Gets the copy status of an Azure Storage blob.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageBlobCopyState [-Blob] <String> [-Container] <String> [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-ServerTimeoutPerRequest <Int32]>]
 [-WaitForComplete]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageBlobCopyState [-Blob] <String> [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-ServerTimeoutPerRequest <Int32]>]
 [-WaitForComplete] -CloudBlobContainer <CloudBlobContainer>
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureStorageBlobCopyState [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-ServerTimeoutPerRequest <Int32]>] [-WaitForComplete] -CloudBlob <CloudBlob>
```

## DESCRIPTION
The **Get-AzureStorageBlobCopyState** cmdlet gets the copy status of an azure_2 Storage blob.

## EXAMPLES

### Example 1: Get the copy status of a blob
```
C:\PS>Get-AzureStorageBlobCopyState -Blob "ContosoPlanning2015" -Container "ContosoUploads"
```

This command gets the copy status of the blob named ContosoPlanning2015 in the container ContosoUploads.

### Example 2: Get the copy status for of a blob by using the pipeline
```
C:\PS>Get-AzureStorageBlob -Blob "ContosoPlanning2015" -Container "ContosoUploads" | Get-AzureStorageBlobCopyState
```

This command gets the blob named ContosoPlanning2015 in the container named ContosoUploads by using the **Get-AzureStorageBlob** cmdlet, and then passes the result to the current cmdlet by using the pipeline operator.
The **Get-AzureStorageBlobCopyState** cmdlet gets the copy status for that blob.

### Example 3: Get the copy status for a blob in a container by using the pipeline
```
C:\PS>Get-AzureStorageContainer -Name "ContosoUploads" | Get-AzureStorageBlobCopyState -Blob "ContosoPlanning2015"
```

This command gets the container named by using the **Get-AzureStorageBlob** cmdlet, and then passes the result to the current cmdlet.
The **Get-AzureStorageContainer** cmdlet gets the copy status for the blob named ContosoPlanning2015 in that container.

## PARAMETERS

### -Blob
Specifies the name of a blob.
This cmdlet gets the state of the blob copy operation for the azure_2 Storage blob that this parameter specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientTimeoutPerRequest
Specifies the client-side time-out interval, in seconds, for one service request.
If the previous call fails in the specified interval, this cmdlet retries the request.
If this cmdlet does not receive a successful response before the interval elapses, this cmdlet returns an error.

```yaml
Type: Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudBlob
Specifies a **CloudBlob** object from azure_2 Storage Client library.
To obtain a **CloudBlob** object, use the Get-AzureStorageBlob cmdlet.

```yaml
Type: CloudBlob
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: ICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -CloudBlobContainer
Specifies a **CloudBlobContainer** object from the azure_2 Storage Client library.
This cmdlet gets the copy status of a blob in the container that this parameter specifies.
To obtain a **CloudBlobContainer** object, use the Get-AzureStorageContainer cmdlet.

```yaml
Type: CloudBlobContainer
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Specifies the maximum concurrent network calls.
You can use this parameter to limit the concurrency to throttle local CPU and bandwidth usage by specifying the maximum number of concurrent network calls.
The specified value is an absolute count and is not multiplied by the core count.
This parameter can help reduce network connection problems in low bandwidth environments, such as 100 kilobits per second.
The default value is 10.

```yaml
Type: Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Container
Specifies the name of a container.
This cmdlet gets the copy status for a blob in the container that this parameter specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Specifies an azure_2 storage context.
To obtain a storage context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Specifies the service side time-out interval, in seconds, for a request.
If the specified interval elapses before the service processes the request, the storage service returns an error.

```yaml
Type: Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitForComplete
Indicates that this cmdlet waits for the copy to finish.
If you do not specify this parameter, this cmdlet returns a result immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### CopyState

## NOTES

## RELATED LINKS

[Start-AzureStorageBlobCopy](606cb5d3-e7fd-4647-b980-329334abc795)

[Stop-AzureStorageBlobCopy](c75b9de9-597d-4986-980e-10e49eeef4a7)

