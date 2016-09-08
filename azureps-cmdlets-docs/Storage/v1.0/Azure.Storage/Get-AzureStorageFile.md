---
external help file: RMAzure_Storage.xml
online version: 7e23b9f6-5f66-49a3-beb8-e2639c5234d7
schema: 2.0.0
---

# Get-AzureStorageFile
## SYNOPSIS
Lists directories and files for a path.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageFile [-ShareName] <String> [[-Path] <String>]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageFile [-Share] <CloudFileShare> [[-Path] <String>]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureStorageFile [-Directory] <CloudFileDirectory> [[-Path] <String>]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
```

## DESCRIPTION
The **Get-AzureStorageFile** cmdlet lists directories and files for the share or directory that you specify.
Specify the *Path* parameter to get an instance of a directory or file in the specified path.

This cmdlet returns **AzureStorageFile** and **AzureStorageDirectory** objects.
You can use the **IsDirectory** property to distinguish between folders and files.

## EXAMPLES

### Example 1: List directories in a share
```
PS C:\>Get-AzureStorageFile -ShareName "share1" | where {$_.GetType().Name -eq "CloudFileDirectory"}
```

This command lists only the directories in the share ContosoShare06.
It first retrieves both files and directories, passes them to the **where** operator by using the pipeline operator, then discards any objects whose type is not "CloudFileDirectory".

### Example 2: List a File Directory
```
PS C:\> Get-AzureStorageFile -ShareName "ContosoShare06" â€"Path "ContosoWorkingFolder" | Get-AzureStorageFile
```

This command lists the files and folders in the directory ContosoWorkingFolder under the share ContosoShare06.
It first gets the directory instance, and then pipelines it to the **Get-AzureStorageFile** cmdlet to list the directory.

## PARAMETERS

### -ClientTimeoutPerRequest
Specifies the client side time-out interval, in seconds, for one service request.
If the previous call fails within the specified interval, this cmdlet retries the request.
If this cmdlet does not receive a successful response before the interval elapses, this cmdlet returns an error.

```yaml
Type: Nullable [System.Int32]
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
This parameter can help mitigate network connection problems in low bandwidth environments, such as 100 kilobits per second.
The default value is 10.

```yaml
Type: Nullable [System.Int32]
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
To obtain a Storage context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Directory
Specifies a folder as a **CloudFileDirectory** object.
This cmdlet gets the folder that this parameter specifies.
To obtain a directory, use the New-AzureStorageDirectory cmdlet.
You can also use the **Get-AzureStorageFile** cmdlet to obtain a directory.

```yaml
Type: CloudFileDirectory
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path of a folder.

If you omit the *Path* parameter, **Get-AzureStorageFile** lists the directories and files in the specified file share or directory.
If you include the *Path* parameter, **Get-AzureStorageFile** returns an instance of a directory or file in the specified path.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Specifies the service-side timeout interval, in seconds, for a request.
If the specified interval elapses before the service processes the request, the Storage service returns an error.

```yaml
Type: Nullable [System.Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Share
Specifies a **CloudFileShare** object.
This cmdlet gets a file or directory from the file share that this parameter specifies.
To obtain a **CloudFileShare** object, use the Get-AzureStorageShare cmdlet.
This object contains the Storage context.
If you specify this parameter, do not specify the *Context* parameter.

```yaml
Type: CloudFileShare
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -ShareName
Specifies the name of the file share.
This cmdlet gets a file or directory from the file share that this parameter specifies.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageFileContent](7e23b9f6-5f66-49a3-beb8-e2639c5234d7)

[New-AzureStorageDirectory](2eea330c-759d-4dee-81e9-2e72de9f707e)

[Remove-AzureStorageDirectory](2cbd0756-0224-43b0-8e22-a7316b7e24c2)

[Remove-AzureStorageFile](c9eb0c34-12ba-4978-85b5-f52c71e9ddf3)

[Set-AzureStorageFileContent](cd2e0aa7-3259-4aa5-8494-c432063d34e7)

