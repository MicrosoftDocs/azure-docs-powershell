---
external help file: RMAzure_Storage.xml
online version: 15371eb7-da6a-4b26-bbda-b59a2eeedb1d
schema: 2.0.0
---

# Get-AzureStorageBlob
## SYNOPSIS
Lists blobs in a container.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageBlob [[-Blob] <String>] [-Container] <String> [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-ContinuationToken <BlobContinuationToken>]
 [-MaxCount <Int32]>] [-ServerTimeoutPerRequest <Int32]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageBlob [-Container] <String> [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-ContinuationToken <BlobContinuationToken>] [-MaxCount <Int32]>]
 [-Prefix <String>] [-ServerTimeoutPerRequest <Int32]>]
```

## DESCRIPTION
The **Get-AzureStorageBlob** cmdlet lists blobs in the specified container in an Azure storage account.

## EXAMPLES

### Example 1: Get a blob by blob name
```
PS C:\>Get-AzureStorageBlob -Container "ContainerName" -Blob blob*
```

This command uses a blob name and wildcard to get a blob.

### Example 2: Get a blob by using the pipeline
```
PS C:\>Get-AzureStorageContainer -Name container* | Get-AzureStorageBlob
```

This command uses the pipeline to get a blob.

### Example 3: Get a blob by name prefix
```
PS C:\>Get-AzureStorageBlob -Container "ContainerName" -Prefix "blob"
```

This command uses a name prefix to get a blob.

### Example 4: List blobs in multiple batches
```
PS C:\>$MaxReturn = 10000
PS C:\> $ContainerName = "abc"
PS C:\> $Total = 0
PS C:\> $Token = $Null
PS C:\> do
 {
     $Blobs = Get-AzureStorageBlob -Container $ContainerName -MaxCount $MaxReturn  -ContinuationToken $Token
     $Total += $Blobs.Count
     if($Blobs.Length -le 0) { Break;}
     $Token = $Blobs[$blobs.Count -1].ContinuationToken;
 }
 While ($Token -ne $Null)
PS C:\> Echo "Total $Total blobs in container $ContainerName"
```

This example uses the *MaxCount* and *ContinuationToken* parameters to list azure_2 Storage blobs in multiple batches.
The first four commands assign values to variables to use in the example.

The fifth command specifies a **Do-While** statement that uses the **Get-AzureStorageBlob** cmdlet to get blobs.
The statement includes the continuation token stored in the $Token variable.
$Token changes value as the loop runs.
For more information, type \[CODE_Snippit\]Get-Help About_Do\[CODE_Snippit\].

The final command uses the **Echo** command to display the total.

## PARAMETERS

### -Blob
Specifies a name or name pattern, which can be used for a wildcard search.
If no blob name is specified, the cmdlet lists all the blobs in the specified container.
If a value is specified for this parameter, the cmdlet lists all blobs with names that match this parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
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
Specifies the name of the container.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Context
Specifies the Azure storage account from which you want to get a list of blobs.
You can use the New-AzureStorageContext cmdlet to create a storage context.

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

### -ContinuationToken
Specifies a continuation token for the blob list.
Use this parameter and the *MaxCount* parameter to list blobs in multiple batches.

```yaml
Type: BlobContinuationToken
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCount
Specifies the maximum number of objects that this cmdlet returns.

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

### -Prefix
Specifies a prefix for the blob names that you want to get.
This parameter does not support using regular expressions or wildcard characters to search.
This means that if the container has only blobs named "My", "MyBlob1", and "MyBlob2" and you specify "-Prefix My*", the cmdlet returns no blobs.
However, if you specify "-Prefix My", the cmdlet returns "My", "MyBlob1", and "MyBlob2".

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

## INPUTS

## OUTPUTS

### AzureStorageBlob

## NOTES
SYNOPSIS

## RELATED LINKS

[Get-AzureStorageBlobContent](15371eb7-da6a-4b26-bbda-b59a2eeedb1d)

[Remove-AzureStorageBlob](fddc1b9e-caf4-47d7-a6b2-a2b2bb50113a)

[Set-AzureStorageBlobContent](c3d50900-70d6-44af-b939-abe86fcf89e6)

