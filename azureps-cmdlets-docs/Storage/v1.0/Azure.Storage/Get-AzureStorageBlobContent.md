---
external help file: RMAzure_Storage.xml
online version: c3d50900-70d6-44af-b939-abe86fcf89e6
schema: 2.0.0
---

# Get-AzureStorageBlobContent
## SYNOPSIS
Downloads a storage blob.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageBlobContent [-Blob] <String> [-Container] <String> [-CheckMd5]
 [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>]
 [-Destination <String>] [-Force] [-ServerTimeoutPerRequest <Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageBlobContent [-Blob] <String> [-CheckMd5] [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-Destination <String>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -CloudBlobContainer <CloudBlobContainer> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureStorageBlobContent [-CheckMd5] [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-Destination <String>] [-Force] [-ServerTimeoutPerRequest <Int32]>]
 -CloudBlob <CloudBlob> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Get-AzureStorageBlobContent** cmdlet downloads the specified storage blob.
If the blob name is not valid for the local computer, this cmdlet automatically resolves it if it is possible.

## EXAMPLES

### Example 1: Download blob content by name
```
PS C:\>Get-AzureStorageBlobContent -Container "ContainerName" -Blob "Blob" -Destination "C:\test\"
```

This command downloads a blob by name.

### Example 2: Download blob content using the pipeline
```
PS C:\>Get-AzureStorageBlob -Container containername -Blob blobname | Get-AzureStorageBlobContent
```

This command uses the pipeline to find and download blob content.

### Example 3: Download blob content using the pipeline and a wildcard character
```
PS C:\>Get-AzureStorageContainer container* | Get-AzureStorageBlobContent -Blob "cbox.exe" -Destination "C:\test"
```

This example uses the asterisk wildcard character and the pipeline to find and download blob content.

## PARAMETERS

### -Blob
Specifies the name of the blob to be downloaded.

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

### -CheckMd5
Specifies whether to check the Md5 sum for the downloaded file.

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
Specifies a **CloudBlobContainer** object from the azure_2 storage client library.
You can create it or use the Get-AzureStorageContainer cmdlet.

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
Specifies the name of container that has the blob you want to download.

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
Specifies the Azure storage account from which you want to download blob content.
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

### -Destination
Specifies the location to store the downloaded file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Overwrites an existing file without confirmation.

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

### AzureStorageContainer

## NOTES
If the blob name is invalid for local computer, this cmdlet autoresolves it, if it is possible.

## RELATED LINKS

[Set-AzureStorageBlobContent](c3d50900-70d6-44af-b939-abe86fcf89e6)

[Get-AzureStorageBlob](74bc4494-be41-4493-9939-e51e61dd09e6)

[Remove-AzureStorageBlob](fddc1b9e-caf4-47d7-a6b2-a2b2bb50113a)

