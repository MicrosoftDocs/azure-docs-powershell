---
external help file: RMAzure_Storage.xml
online version: d9ec4b6f-fb17-4f29-b209-a3d5f212a6f1
schema: 2.0.0
---

# Remove-AzureStorageFile
## SYNOPSIS
Deletes a file.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-AzureStorageFile [-ShareName] <String> [-Path] <String>
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-AzureStorageFile [-Share] <CloudFileShare> [-Path] <String>
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-AzureStorageFile [-Directory] <CloudFileDirectory> [-Path] <String>
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Remove-AzureStorageFile [-File] <CloudFile> [-ClientTimeoutPerRequest <Nullable [System.Int32]>]
 [-ConcurrentTaskCount <Nullable [System.Int32]>] [-PassThru]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureStorageFile** cmdlet deletes a file.

## EXAMPLES

### Example 1: Delete a file from a file share
```
PS C:\>Remove-AzureStorageFile -ShareName "ContosoShare06" -Path "ContosoFile22"
```

This command deletes the file that is named ContosoFile22 from the file share named ContosoShare06.

### Example 2: Get a file from a file share by using a file share object
```
PS C:\>Get-AzureStorageShare -Name "ContosoShare06" | Remove-AzureStorageFile -Path "ContosoFile22"
```

This command uses the **Get-AzureStorageShare** cmdlet to get the file share named ContosoShare06, and then passes that object to the current cmdlet by using the pipeline operator.
The current command deletes the file that is named ContosoFile22 from ContosoShare06.

## PARAMETERS

### -ClientTimeoutPerRequest
@{Text=}

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
@{Text=}

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
@{Text=}

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
This cmdlet removes a file in the folder that this parameter specifies.

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
This cmdlet removes the file that this parameter specifies.
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

### -PassThru
@{Text=}

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
This cmdlet deletes the file that this parameter specifies.

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
@{Text=}

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
This cmdlet removes the file in the share this parameter specifies.
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
This cmdlet removes the file in the share this parameter specifies.

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

[Get-AzureStorageShare](10a13c83-d545-4729-99f9-048c774f32d7)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

