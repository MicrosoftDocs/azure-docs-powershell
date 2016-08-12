---
external help file: RMAzure_Storage.xml
online version: 15371eb7-da6a-4b26-bbda-b59a2eeedb1d
schema: 2.0.0
---

# Set-AzureStorageBlobContent
## SYNOPSIS
Uploads a local file to an azure_2 Storage blob.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-AzureStorageBlobContent [-File] <String> [-Container] <String> [-Blob <String>] [-BlobType]
 [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-Force]
 [-Metadata <Hashtable>] [-Properties <Hashtable>] [-ServerTimeoutPerRequest <Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-AzureStorageBlobContent [-File] <String> [-Blob <String>] [-BlobType] [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-Force] [-Metadata <Hashtable>]
 [-Properties <Hashtable>] [-ServerTimeoutPerRequest <Int32]>] -CloudBlobContainer <CloudBlobContainer>
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-AzureStorageBlobContent [-File] <String> [-BlobType] [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-Force] [-Metadata <Hashtable>]
 [-Properties <Hashtable>] [-ServerTimeoutPerRequest <Int32]>] -CloudBlob <CloudBlob> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-AzureStorageBlobContent** cmdlet uploads a local file to an azure_2 Storage blob.

## EXAMPLES

### Example 1: Upload a named file
```
PS C:\>Set-AzureStorageBlobContent -Container "ContosoUpload" -File ".\PlanningData" -Blob "Planning2015"
```

This command uploads the file that is named PlanningData to a blob named Planning2015.

### Example 2: Upload all files under the current folder
```
PS C:\>Get-ChildItem -File -Recurse | Set-AzureStorageBlobContent -Container "ContosoUploads"
```

This command uses the core powershell cmdlet Get-ChildItem to get all the files in the current folder and in subfolders, and then passes them to the current cmdlet by using the pipeline operator.
The **Set-AzureStorageBlobContent** cmdlet uploads the files to the container named ContosoUploads.

### Example 3: Overwrite an existing blob
```
PS C:\>Get-AzureStorageBlob -Container "ContosoUploads" -Blob "Planning2015" | Set-AzureStorageBlobContent -File "ContosoPlanning"
```

This command gets the blob named Planning2015 in the ContosoUploads container by using the Get-AzureStorageBlob cmdlet, and then passes that blob to the current cmdlet.
The command uploads the file that is named ContosoPlanning as Planning2015.
This command does not specify the *Force* parameter.
The command prompts you for confirmation.
If you confirm the command, the cmdlet overwrites the existing blob.

### Example 4: Upload a file to a container by using the pipeline
```
PS C:\>Get-AzureStorageContainer -Container "ContosoUpload*" | Set-AzureStorageBlobContent -File "ContosoPlanning" -Blob "Planning2015"
```

This command gets the container that starts with the string ContosoUpload by using the **Get-AzureStorageContainer** cmdlet, and then passes that blob to the current cmdlet.
The command uploads the file that is named ContosoPlanning as Planning2015.

### Example 5: Upload a file and metadata
```
PS C:\>$Metadata = @{"key" = "value"; "name" = "test"}
PS C:\> Set-AzureStorageBlobContent -File "ContosoPlanning" -Container "ContosoUploads" -Metadata $Metadata
```

The first command creates a hash table that contains metadata for a blob, and stores that hash table in the $Metadata variable.

The second command uploads the file that is named ContosoPlanning to the container named ContosoUploads.
The blob includes the metadata stored in $Metadata.

## PARAMETERS

### -Blob
Specifies the name of a blob.
This cmdlet uploads a file to the azure_2 Storage blob that this parameter specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobType
Specifies the type for the blob that this cmdlet uploads.
psdx_paramvalues

-- Block
-- Page

The default value is Block.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Block, Page, Append

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
Specifies a **CloudBlob** object.
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
This cmdlet uploads content to a blob in the container that this parameter specifies.
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
This cmdlet uploads a file to a blob in the container that this parameter specifies.

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

### -File
Specifies a local file path for a file to upload as blob content.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: FullName

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: FullName

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet overwrites an existing blob without prompting you for confirmation.

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

### -Metadata
Specifies metadata for the uploaded blob.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties
Specifies properties for the uploaded blob.

```yaml
Type: Hashtable
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

## NOTES

## RELATED LINKS

[Get-AzureStorageBlobContent](15371eb7-da6a-4b26-bbda-b59a2eeedb1d)

[Get-AzureStorageBlob](74bc4494-be41-4493-9939-e51e61dd09e6)

[Remove-AzureStorageBlob](fddc1b9e-caf4-47d7-a6b2-a2b2bb50113a)

