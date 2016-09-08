---
external help file: RMAzure_Storage.xml
online version: d9ec4b6f-fb17-4f29-b209-a3d5f212a6f1
schema: 2.0.0
---

# Stop-AzureStorageFileCopy
## SYNOPSIS
Stops a copy operation to the specified destination file.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Stop-AzureStorageFileCopy [-ShareName] <String> [-FilePath] <String>
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-CopyId <String>] [-Force]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Stop-AzureStorageFileCopy [-File] <CloudFile> [-ClientTimeoutPerRequest <Nullable [System.Int32]>]
 [-ConcurrentTaskCount <Nullable [System.Int32]>] [-CopyId <String>] [-Force]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-AzureStorageFileCopy** cmdlet stops copying a file to a destination file.

## EXAMPLES

### Example 1: Stop a copy operation
```
PS C:\>Stop-AzureStorageFileCopy -ShareName "ContosoShare" -FilePath "FilePath" -CopyId "CopyId"
```

This command stops copying a file that has the specified name.

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

### -CopyId
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Specifies the path of a file.

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

### -Force
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

[Get-AzureStorageFileCopyState](248556e1-291f-4d27-b2e1-e00cc895b3a9)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[Start-AzureStorageFileCopy](66445d9f-72a9-44e3-9f1b-72ec0888357a)

