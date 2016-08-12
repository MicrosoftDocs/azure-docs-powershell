---
external help file: RMAzure_Storage.xml
online version: 5ead5288-78e9-4ebb-904e-5e86ea88da93
schema: 2.0.0
---

# Start-AzureStorageBlobCopy
## SYNOPSIS
Starts to copy a blob.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -AbsoluteUri <String> -DestBlob <String> -DestContainer <String>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Start-AzureStorageBlobCopy [-SrcBlob] <String> [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-DestBlob <String>]
 [-DestContext <AzureStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32]>] -DestContainer <String>
 -SrcContainer <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -CloudBlob <CloudBlob> -DestCloudBlob <CloudBlob> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestBlob <String>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -CloudBlob <CloudBlob> -DestContainer <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Start-AzureStorageBlobCopy [-SrcBlob] <String> [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-DestBlob <String>]
 [-DestContext <AzureStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32]>]
 -CloudBlobContainer <CloudBlobContainer> -DestContainer <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestBlob <String>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestContainer <String> -SrcFilePath <String> -SrcShareName <String>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_7
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestBlob <String>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestContainer <String> -SrcFilePath <String> -SrcShare <CloudFileShare>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_8
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestBlob <String>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestContainer <String> -SrcDir <CloudFileDirectory> -SrcFilePath <String>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_9
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestCloudBlob <CloudBlob> -SrcFile <CloudFile> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_10
```
Start-AzureStorageBlobCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestBlob <String>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestContainer <String> -SrcFile <CloudFile> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-AzureStorageBlobCopy** cmdlet starts to copy a blob.

## EXAMPLES

### Example 1: Copy a named blob
```
C:\PS>Start-AzureStorageBlobCopy -SrcBlob "ContosoPlanning2015" -DestContainer "ContosoArchives" -SrcContainer "ContosoUploads"
```

This command starts the copy operation of the blob named ContosoPlanning2015 from the container named ContosoUploads to the container named ContosoArchives.

### Example 2: Get a container to specify blobs to copy
```
C:\PS>Get-AzureStorageContainer -Name "ContosoUploads" | Start-AzureStorageBlobCopy -SrcBlob "ContosoPlanning2015" -DestContainer "ContosoArchives"
```

This command gets the container named ContosoUploads, by using the **Get-AzureStorageContainer** cmdlet, and then passes the container to the current cmdlet by using the pipeline operator.
That cmdlet starts the copy operation of the blob named ContosoPlanning2015.
The previous cmdlet provides the source container.
The *DestContainer* parameter specifies ContosoArchives as the destination container.

### Example 3: Get a blob to copy
```
C:\PS>Get-AzureStorageBlob -Container "ContosoUploads" | Start-AzureStorageBlobCopy -DestContainer "ContosoArchives"
```

This command gets the blobs in the container named ContosoUploads, by using the **Get-AzureStorageBlob** cmdlet, and then passes the results to the current cmdlet by using the pipeline operator.
That cmdlet starts the copy operation of the blobs to the container named ContosoArchives.

### Example 4: Copy a blob specified as an object
```
C:\PS>$SrcBlob = Get-AzureStorageBlob -Container "ContosoUploads" -Blob "ContosoPlanning2015"
C:\PS> $DestBlob = Get-AzureStorageBlob -Container "ContosoArchives" -Blob "ContosoPlanning2015Archived"
C:\PS> Start-AzureStorageBlobCopy -ICloudBlob $SrcBlob.ICloudBlob -DestICloudBlob $DestBlob.ICloudBlob
```

The first command gets the blob named ContosoPlanning2015 in the container named ContosoUploads.
The command stores that object in the $SrcBlob variable.

The second command gets the blob named ContosoPlanning2015Archived in the container named ContosoArchives.
The command stores that object in the $DestBlob variable.

The last command starts the copy operation from the source container to the destination container.
The command uses standard dot notation to specify the **ICloudBlob** objects for the $SrcBlob and $DestBlob blobs.

### Example 5: Copy a blob from a URI
```
C:\PS>$Context = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
C:\PS> Start-AzureStorageBlobCopy -AbsoluteUri "http://www.contosointernal.com/planning" -DestContainer "ContosoArchive" -DestBlob "ContosoPlanning2015" -DestContext $Context
```

This command creates a context for the account named ContosoGeneral that uses the specified key, and then stores that key in the $Context variable.

The second command copies the file from the specified URI to the blob named ContosoPlanning in the container named ContosoArchive.
The command starts the copy operation in the context stored in $Context.

## PARAMETERS

### -AbsoluteUri
Specifies the absolute URI of a file to copy to an azure_2 Storage blob.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: SrcUri

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: SrcICloudBlob,SrcCloudBlob,ICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -CloudBlobContainer
Specifies a **CloudBlobContainer** object from the azure_2 Storage Client library.
This cmdlet copies a blob from the container that this parameter specifies.
To obtain a **CloudBlobContainer** object, use the Get-AzureStorageContainer cmdlet.

```yaml
Type: CloudBlobContainer
Parameter Sets: UNNAMED_PARAMETER_SET_5
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

### -Context
Specifies an azure_2 storage context.
To obtain a storage context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: SrcContext

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10
Aliases: SrcContext

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestBlob
Specifies the name of the destination blob.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_10
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestCloudBlob
Specifies a destination **CloudBlob** object

```yaml
Type: CloudBlob
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_9
Aliases: DestICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestContainer
Specifies the name of the destination container.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_10
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestContext
Specifies an azure_2 storage context.
To obtain a storage context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet overwrites the destination blob without prompting you for confirmation.

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

### -SrcBlob
Specifies the name of the source blob.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcContainer
Specifies the name of the source container.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcDir
Specifies a **CloudFileDirectory** object from azure_2 Storage Client library.

```yaml
Type: CloudFileDirectory
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcFile
Specifes a **CloudFile** object from azure_2 Storage Client library.
You can create it or use Get-AzureStorageFile cmdlet.

```yaml
Type: CloudFile
Parameter Sets: UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -SrcFilePath
Specifies the source file relative path of source directory or source share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShare
Specifies a **CloudFileShare** object from azure_2 Storage Client library.
You can create it or use Get-AzureStorageShare cmdlet.

```yaml
Type: CloudFileShare
Parameter Sets: UNNAMED_PARAMETER_SET_7
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShareName
Specifies the source share name.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
psdx_confirmdesc

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

### -WhatIf
psdx_whatifdesc

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

[Get-AzureStorageBlobCopyState](5ead5288-78e9-4ebb-904e-5e86ea88da93)

[Stop-AzureStorageBlobCopy](c75b9de9-597d-4986-980e-10e49eeef4a7)

