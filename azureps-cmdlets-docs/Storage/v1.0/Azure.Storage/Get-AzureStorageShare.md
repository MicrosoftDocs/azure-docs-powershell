---
external help file: RMAzure_Storage.xml
online version: 17c0253c-c7b6-4c78-92ce-77277e156396
schema: 2.0.0
---

# Get-AzureStorageShare
## SYNOPSIS
Gets a list of file shares.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageShare [[-Prefix] <String>] [-ClientTimeoutPerRequest <Nullable [System.Int32]>]
 [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Context <AzureStorageContext>]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageShare [-Name] <String> [-ClientTimeoutPerRequest <Nullable [System.Int32]>]
 [-ConcurrentTaskCount <Nullable [System.Int32]>] [-Context <AzureStorageContext>]
 [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
```

## DESCRIPTION
The **Get-AzureStorageShare** cmdlet gets a list of file shares for a storage account.

## EXAMPLES

### Example 1: Get a file share
```
PS C:\>Get-AzureStorageShare -Name "ContosoShare06"
```

This command gets the file share named ContosoShare06.

### Example 2: Get all file shares that begin with a string
```
PS C:\>Get-AzureStorageShare -Prefix "Contoso"
```

This command gets all file shares that have names that begin with Contoso.

### Example 3: Get all file shares in a specified context
```
PS C:\>$Context = New-AzureStorageContext -Local
PS C:\> Get-AzureStorageShare -Context $Context
```

The first command uses the **New-AzureStorageContext** cmdlet to create a context by using the *Local* parameter, and then stores that context object in the $Context variable.

The second command gets the file shares for the context object stored in $Context.

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
Specifies the name of the file share.
This cmdlet gets the file share that this parameter specifies, or nothing if you specify the name of a file share that does not exist.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefix
Specifies the prefix for file shares.
This cmdlet gets file shares that match the prefix that this parameter specifies, or no file shares if no file shares match the specified prefix.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageShare](17c0253c-c7b6-4c78-92ce-77277e156396)

[Remove-AzureStorageShare](f9a0f4e1-3677-4786-bd84-d3645c61baca)

