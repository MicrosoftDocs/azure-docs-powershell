---
external help file: RMAzure_Storage.xml
online version: d9ec4b6f-fb17-4f29-b209-a3d5f212a6f1
schema: 2.0.0
---

# Get-AzureStorageFileCopyState
## SYNOPSIS
Gets the state of a copy operation.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageFileCopyState [-ShareName] <String> [-FilePath] <String>
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-WaitForComplete]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageFileCopyState [-File] <CloudFile> [-ClientTimeoutPerRequest <Nullable [System.Int32]>]
 [-ConcurrentTaskCount <Nullable [System.Int32]>] [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
 [-WaitForComplete]
```

## DESCRIPTION
The **Get-AzureStorageFileCopyState** cmdlet gets the state of an azure_2 Storage file copy operation.

## EXAMPLES

### Example 1: Get the copy state by file name
```
PS C:\>Get-AzureStorageFileCopyState -ShareName "ContosoShare" -FilePath "ContosoFile"
```

This command gets the state of the copy operation for a file that has the specified name.

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

### -File
Specifies a **CloudFile** object.
You can create a cloud file or obtain one by using the Get-AzureStorageFile cmdlet.

```yaml
Type: CloudFile
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue)
Accept wildcard characters: False
```

### -FilePath
Specifies the path of the file relative to an azure_2 Storage share.

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

### -ShareName
Specifies the name of a share.

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

### -WaitForComplete
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageFile](d9ec4b6f-fb17-4f29-b209-a3d5f212a6f1)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[Start-AzureStorageFileCopy](66445d9f-72a9-44e3-9f1b-72ec0888357a)

[Stop-AzureStorageFileCopy](abc5a8cb-1151-4d5c-9230-d5c3a44f5a4c)

