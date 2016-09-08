---
external help file: RMAzure_Storage.xml
online version: 74bc4494-be41-4493-9939-e51e61dd09e6
schema: 2.0.0
---

# Remove-AzureStorageBlob
## SYNOPSIS
Removes the specified storage blob.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-AzureStorageBlob [-Blob] <String> [-Container] <String> [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-DeleteSnapshot] [-Force] [-PassThru]
 [-ServerTimeoutPerRequest <Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-AzureStorageBlob [-Blob] <String> [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DeleteSnapshot] [-Force] [-PassThru] [-ServerTimeoutPerRequest <Int32]>]
 -CloudBlobContainer <CloudBlobContainer> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-AzureStorageBlob [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DeleteSnapshot] [-Force] [-PassThru] [-ServerTimeoutPerRequest <Int32]>]
 -CloudBlob <CloudBlob> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureStorageBlob** cmdlet removes the specified blob from a storage account in azure_2.

## EXAMPLES

### Example 1: Remove a storage blob by name
```
PS C:\>Remove-AzureStorageBlob -Container "ContainerName" -Blob "BlobName"
```

This command removes a blob identified by its name.

### Example 2: Remove a storage blob using the pipeline
```
PS C:\>Get-AzureStorageBlob -Container "ContainerName" -Blob "BlobName" | Remove-AzureStorageBlob
```

This command uses the pipeline.

### Example 3: Remove storage blobs using the pipeline
```
PS C:\>Get-AzureStorageContainer -Container container* | Remove-AzureStorageBlob -Blob "BlobName"
```

This command uses the asterisk (*) wildcard character and the pipeline to retrieve the blob or blobs and then removes them.

## PARAMETERS

### -Blob
Specifies the name of the blob you want to remove.

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
Specifies a cloud blob.
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
You can use the Get-AzureStorageContainer cmdlet to get it.

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
Specifies the name of the container.

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
Specifies the azure_2 storage context.
You can use the New-AzureStorageContext cmdlet to create it.

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

### -DeleteSnapshot
Specifies that all snapshots be deleted, but not the base blob.
If this parameter is not specified, the base blob and its snapshots are deleted together.
The user is prompted to confirm the delete operation.

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

### -Force
Indicates that this cmdlet removes the blob and its snapshot without confirmation.

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

### -PassThru
Indicates that this cmdlet returns a **Boolean** that reflects the success of the operation.
By default, this cmdlet does not return a value.

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
Specifies the azure_2 profile for the cmdlet to read.
If not specified, the cmdlet reads from the default profile.

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

[Get-AzureStorageBlob](74bc4494-be41-4493-9939-e51e61dd09e6)

[Get-AzureStorageBlobContent](15371eb7-da6a-4b26-bbda-b59a2eeedb1d)

[Set-AzureStorageBlobContent](c3d50900-70d6-44af-b939-abe86fcf89e6)

