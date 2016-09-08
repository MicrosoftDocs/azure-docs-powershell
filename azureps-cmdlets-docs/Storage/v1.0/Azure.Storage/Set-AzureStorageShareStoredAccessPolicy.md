---
external help file: RMAzure_Storage.xml
online version: d3ad790c-c75f-4243-b128-7c778422ac64
schema: 2.0.0
---

# Set-AzureStorageShareStoredAccessPolicy
## SYNOPSIS
Updates a stored access policy on a Storage share.

## SYNTAX

```
Set-AzureStorageShareStoredAccessPolicy [-ShareName] <String> [-Policy] <String>
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-ExpiryTime <Nullable [System.DateTime]>] [-NoExpiryTime] [-NoStartTime]
 [-Permission <String>] [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
 [-StartTime <Nullable [System.DateTime]>]
```

## DESCRIPTION
The **Set-AzureStorageShareStoredAccessPolicy** cmdlet updates stored access policy on an azure_2 Storage share.

## EXAMPLES

### Example 1: Update a stored access policy in Storage share
```
PS C:\>Set-AzureStorageShareStoredAccessPolicy -ShareName "ContosoShare" -Policy "GeneralPolicy" -Permission "rwdl"
```

This command updates a stored access policy that has full permission in a share.

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

### -ExpiryTime
@{Text=}

```yaml
Type: Nullable [System.DateTime]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoExpiryTime
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

### -NoStartTime
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

### -Permission
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

### -Policy
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
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
Specifies the name of the Storage share.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
@{Text=}

```yaml
Type: Nullable [System.DateTime]
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

[Get-AzureStorageShareStoredAccessPolicy](d3ad790c-c75f-4243-b128-7c778422ac64)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[New-AzureStorageShareStoredAccessPolicy](d5b956f0-92ca-4246-9860-dfa96f17ed8a)

[Remove-AzureStorageShareStoredAccessPolicy](af46a7c9-dd40-4d0d-9950-56f661dada33)

