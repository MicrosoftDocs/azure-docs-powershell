---
external help file: RMAzure_Storage.xml
online version: 10a13c83-d545-4729-99f9-048c774f32d7
schema: 2.0.0
---

# New-AzureStorageShare
## SYNOPSIS
Creates a file share.

## SYNTAX

```
New-AzureStorageShare [-Name] <String> [-ClientTimeoutPerRequest <Nullable [System.Int32]>]
 [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Context <AzureStorageContext>]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
```

## DESCRIPTION
The **New-AzureStorageShare** cmdlet creates a file share.

## EXAMPLES

### Example 1: Create a file share
```
PS C:\>New-AzureStorageShare -Name "ContosoShare06"
```

This command creates a file share named ContosoShare06.

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Name
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageShare](10a13c83-d545-4729-99f9-048c774f32d7)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[Remove-AzureStorageShare](f9a0f4e1-3677-4786-bd84-d3645c61baca)

