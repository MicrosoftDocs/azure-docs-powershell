---
external help file: RMAzure_Storage.xml
online version: 00a693d9-52d2-4c9b-9d7b-e476ca51a610
schema: 2.0.0
---

# Get-AzureStorageContainerStoredAccessPolicy
## SYNOPSIS
Gets the stored access policy or policies for an azure_2 storage container.

## SYNTAX

```
Get-AzureStorageContainerStoredAccessPolicy [-Container] <String> [[-Policy] <String>]
 [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>]
 [-ServerTimeoutPerRequest <Int32]>]
```

## DESCRIPTION
The **Get-AzureStorageContainerStoredAccessPolicy** cmdlet lists the stored access policy or policies for an azure_2 storage container.

## EXAMPLES

### Example 1: Get a stored access policy in a storage container
```
PS C:\>Get-AzureStorageContainerStoredAccessPolicy -Container "Container07" -Policy "Policy22"
```

This command gets the access policy named Policy22 in the storage container named Container07.

### Example 2: Get all the stored access policies in a storage container
```
PS C:\>Get-AzureStorageContainerStoredAccessPolicy -Container "Container07"
```

This command gets all access policies in the storage container named Container07.

## PARAMETERS

### -ClientTimeoutPerRequest
Specifies the client-side time-out interval, in seconds, for one service request.
If the previous call fails in the specified interval, this cmdlet retries the request.
If this cmdlet does not receive a successful response before the interval elapses, this cmdlet returns an error.

```yaml
Type: Int32]
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
This parameter can help reduce network connection problems in low bandwidth environments, such as 100 kilobits per second.
The default value is 10.

```yaml
Type: Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Container
Specifies the name of your azure_2 storage container.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Context
Specifies the azure_2 storage context.

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
Specifies the azure_2 stored access policy.

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
Specifies the service side time-out interval, in seconds, for a request.
If the specified interval elapses before the service processes the request, the storage service returns an error.

```yaml
Type: Int32]
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

[New-AzureStorageContainerStoredAccessPolicy](00a693d9-52d2-4c9b-9d7b-e476ca51a610)

[Remove-AzureStorageContainerStoredAccessPolicy](60b0802b-aedd-4d2e-a37f-89bb8c63f0d4)

[Set-AzureStorageContainerStoredAccessPolicy](059cf4a7-db04-4ff5-91da-31d38608b99c)

