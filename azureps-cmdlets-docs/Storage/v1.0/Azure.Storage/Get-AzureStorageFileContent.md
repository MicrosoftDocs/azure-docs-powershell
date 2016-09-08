---
external help file: RMAzure_Storage.xml
online version: d9ec4b6f-fb17-4f29-b209-a3d5f212a6f1
schema: 2.0.0
---

# Get-AzureStorageFileContent
## SYNOPSIS
Downloads the contents of a file.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageFileContent [-ShareName] <String> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-Force] [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
 [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageFileContent [-Share] <CloudFileShare> [-Path] <String> [[-Destination] <String>] [-CheckMd5]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Force]
 [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Get-AzureStorageFileContent [-Directory] <CloudFileDirectory> [-Path] <String> [[-Destination] <String>]
 [-CheckMd5] [-ClientTimeoutPerRequest <Nullable [System.Int32]>]
 [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Force] [-PassThru]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Get-AzureStorageFileContent [-File] <CloudFile> [[-Destination] <String>] [-CheckMd5]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Force]
 [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Get-AzureStorageFileContent** cmdlet downloads the contents of a file, and then saves it to a destination that you specify.
This cmdlet does not return the contents of the file.

## EXAMPLES

### Example 1: Download a file from a folder
```
PS C:\>Get-AzureStorageFileContent -ShareName "ContosoShare06" -Path "ContosoWorkingFolder/CurrentDataFile"
```

This command downloads a file that is named CurrentDataFile in the folder ContosoWorkingFolder from the file share ContosoShare06 to current folder.

## PARAMETERS

### -CheckMd5
If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

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
If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

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
If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

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
If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

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

### -Destination
Specifies the destination path.
This cmdlet downloads the file contents to the location that this parameter specifies.

If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Directory
Specifies a folder as a **CloudFileDirectory** object.
This cmdlet gets content for a file in the folder that this parameter specifies.
To obtain a directory, use the New-AzureStorageDirectory cmdlet.
You can also use the Get-AzureStorageFile cmdlet to obtain a directory.

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

### -File
Specifies a file as a **CloudFile** object.
This cmdlet gets the file that this parameter specifies.
To obtain a **CloudFile** object, use the Get-AzureStorageFile cmdlet.

```yaml
Type: CloudFile
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -Force
If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

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
If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

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

### -Path
Specifies the path of a file.
This cmdlet gets the contents the file that this parameter specifies.
If the file does not exist, this cmdlet returns an error.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
If you specify the path of a file that does not exist, this cmdlet creates that file, and saves the contents in the new file.
If you specify a path of a file that already exists and you specify the *Force* parameter, the cmdlet overwrites the file.
If you specify a path of an existing file and you do not specify *Force*, the cmdlet prompts you before it continues.

If you specify the path of a folder, this cmdlet attempts to create a file that has the name of the Azure storage file.

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
This cmdlet downloads the contents of the file in the share this parameter specifies.
To obtain a **CloudFileShare** object, use the Get-AzureStorageShare cmdlet.
This object contains the storage context.
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
This cmdlet downloads the contents of the file in the share this parameter specifies.

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

[Get-AzureStorageFile](d9ec4b6f-fb17-4f29-b209-a3d5f212a6f1)

[Set-AzureStorageFileContent](cd2e0aa7-3259-4aa5-8494-c432063d34e7)

