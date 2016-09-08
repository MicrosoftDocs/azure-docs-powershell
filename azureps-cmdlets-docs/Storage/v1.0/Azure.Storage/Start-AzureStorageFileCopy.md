---
external help file: RMAzure_Storage.xml
online version: 74bc4494-be41-4493-9939-e51e61dd09e6
schema: 2.0.0
---

# Start-AzureStorageFileCopy
## SYNOPSIS
Starts to copy a source file.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-DestContext <AzureStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32]>] -AbsoluteUri <String>
 -DestFilePath <String> -DestShareName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -AbsoluteUri <String> -DestFile <CloudFile> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestFilePath <String> -DestShareName <String> -SrcBlobName <String>
 -SrcContainerName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-DestContext <AzureStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32]>] -DestFilePath <String>
 -DestShareName <String> -SrcBlobName <String> -SrcContainer <CloudBlobContainer> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestFile <CloudFile> -SrcBlob <CloudBlob> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-DestContext <AzureStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32]>] -DestFilePath <String>
 -DestShareName <String> -SrcBlob <CloudBlob> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_7
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-DestContext <AzureStorageContext>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestFilePath <String> -DestShareName <String> -SrcFilePath <String>
 -SrcShareName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_8
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-DestContext <AzureStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32]>] -DestFilePath <String>
 -DestShareName <String> -SrcFilePath <String> -SrcShare <CloudFileShare> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_9
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-DestContext <AzureStorageContext>] [-Force] [-ServerTimeoutPerRequest <Int32]>] -DestFilePath <String>
 -DestShareName <String> -SrcFile <CloudFile> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_10
```
Start-AzureStorageFileCopy [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>] [-Force]
 [-ServerTimeoutPerRequest <Int32]>] -DestFile <CloudFile> -SrcFile <CloudFile> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-AzureStorageFileCopy** cmdlet starts to copy a source file to a destination file.

## EXAMPLES

### Example 1: Start copy operation from file to file by using share name and file name
```
PS C:\>Start-AzureStorageFileCopy -SrcShareName "ContosoShare01" -SrcFilePath "FilePath01" -DestShareName "ContosoShare02" -DestFilePath "FilePath02"
```

This command starts a copy operation from file to file.
The command specifies share name and file name

### Example 2: Start copy operation from blob to file by using container name and blob name
```
PS C:\>Start-AzureStorageFileCopy -SrcContainerName "ContosoContainer01" -SrcBlobName "ContosoBlob01" -DestShareName "ContosoShare" -DestFilePath "FilePath02"
```

This command starts a copy operation from blob to file.
The command specifies container name and blob name

## PARAMETERS

### -AbsoluteUri
Specifies the URI of the source file.
If the source location requires a credential, you must provide one.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
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
Specifies an azure_2 Storage context.
To obtain a context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_7
Aliases: SrcContext

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -DestContext
Specifies the azure_2 Storage context of the destination.
To obtain a context, use **New-AzureStorageContext**.

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestFile
Specifies a **CloudFile** object.
You can create a cloud file or obtain one by using the Get-AzureStorageFile cmdlet.

```yaml
Type: CloudFile
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_10
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestFilePath
Specifies the path of the destination file relative to the destination share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestShareName
Specifies the name of the destination share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_9
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
ps_force

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
Specifies the length of the time-out period for the server part of a request.

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
Specifies a **CloudBlob** object.
You can create a cloud blob or obtain one by using the Get-AzureStorageBlob cmdlet.

```yaml
Type: CloudBlob
Parameter Sets: UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6
Aliases: ICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -SrcBlobName
Specifies the name of the source blob.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcContainer
Specifies a cloud blob container object.
You can create cloud blob container object or use the Get-AzureStorageContainer cmdlet.

```yaml
Type: CloudBlobContainer
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcContainerName
Specifies the name of the source container.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcFile
Specifies a **CloudFile** object.
You can create a cloud file or obtain one by using **Get-AzureStorageFile**.

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
Specifies the path of the source file relative to the source directory or source share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShare
Specifies a cloud file share object.
You can create a cloud file share or obtain one by using the Get-AzureStorageShare cmdlet.

```yaml
Type: CloudFileShare
Parameter Sets: UNNAMED_PARAMETER_SET_8
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcShareName
Specifies the name of the source share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_7
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

[Get-AzureStorageBlob](74bc4494-be41-4493-9939-e51e61dd09e6)

[Get-AzureStorageContainer](4880a1a4-c947-4310-8317-0a837b8acb7f)

[Get-AzureStorageFile](d9ec4b6f-fb17-4f29-b209-a3d5f212a6f1)

[Get-AzureStorageShare](10a13c83-d545-4729-99f9-048c774f32d7)

[Get-AzureStorageFileCopyState](248556e1-291f-4d27-b2e1-e00cc895b3a9)

[Stop-AzureStorageFileCopy](abc5a8cb-1151-4d5c-9230-d5c3a44f5a4c)

