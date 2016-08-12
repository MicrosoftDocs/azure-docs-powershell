---
external help file: RMAzure_Storage.xml
online version: d3ad790c-c75f-4243-b128-7c778422ac64
schema: 2.0.0
---

# Remove-AzureStorageShareStoredAccessPolicy
## SYNOPSIS
Removes a stored access policy from a Storage share.

## SYNTAX

```
Remove-AzureStorageShareStoredAccessPolicy [-ShareName] <String> [-Policy] <String>
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-Force] [-PassThru] [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureStorageShareStoredAccessPolicy** cmdlet removes a stored access policy from an azure_2 Storage share.

## EXAMPLES

### Example 1: Remove a stored access policy from an Azure Storage share
```
PS C:\>Remove-AzureStorageShareStoredAccessPolicy -ShareName "ContosoShare" -Policy "GeneralPolicy"
```

This command removes a stored access policy named GeneralPolicy from ContosoShare.

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

### -Policy
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True(ByPropertyName)
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
Specifies the Storage share name for which this cmdlet removes a policy.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByPropertyName)
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

[Get-AzureStorageShareStoredAccessPolicy](d3ad790c-c75f-4243-b128-7c778422ac64)

[New-AzureStorageShareStoredAccessPolicy](d5b956f0-92ca-4246-9860-dfa96f17ed8a)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[Set-AzureStorageShareStoredAccessPolicy](738f47b7-e244-40b1-9b2e-3b6f4e348c8f)

