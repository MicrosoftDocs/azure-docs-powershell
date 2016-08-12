---
external help file: RMAzure_Storage.xml
online version: 671aeec8-b7f9-49c5-866f-da84f189ab5b
schema: 2.0.0
---

# Get-AzureStorageShareStoredAccessPolicy
## SYNOPSIS
Gets stored access policies for a Storage share.

## SYNTAX

```
Get-AzureStorageShareStoredAccessPolicy [-ShareName] <String> [[-Policy] <String>]
 [-ClientTimeoutPerRequest <Nullable [System.Int32]>] [-ConcurrentTaskCount <Nullable [System.Int32]>]
 [-Context <AzureStorageContext>] [-ServerTimeoutPerRequest <Nullable [System.Int32]>]
```

## DESCRIPTION
The **Get-AzureStorageShareStoredAccessPolicy** cmdlet gets stored access policies for an azure_2 Storage share.
To get a particular policy, specify it by name.

## EXAMPLES

### Example 1: Get a stored access policy in a share
```
PS C:\>Get-AzureStorageShareStoredAccessPolicy -ShareName "ContosoShare" -Policy "GeneralPolicy"
```

This command gets a stored access policy named GeneralPolicy in ContosoShare.

### Example 2: Get all the stored access policies in share
```
PS C:\>Get-AzureStorageShareStoredAccessPolicy -ShareName "ContosoShare"
```

This command gets all stored access policies in ContosoShare.

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

### -Policy
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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
Specifies the Storage share name for which this cmdlet gets policies.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[New-AzureStorageShareStoredAccessPolicy](d5b956f0-92ca-4246-9860-dfa96f17ed8a)

[Remove-AzureStorageShareStoredAccessPolicy](af46a7c9-dd40-4d0d-9950-56f661dada33)

[Set-AzureStorageShareStoredAccessPolicy](738f47b7-e244-40b1-9b2e-3b6f4e348c8f)

