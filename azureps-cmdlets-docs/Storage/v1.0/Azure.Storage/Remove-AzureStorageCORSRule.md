---
external help file: RMAzure_Storage.xml
online version: accfb0fd-ad3a-4415-abce-a98b8073e82b
schema: 2.0.0
---

# Remove-AzureStorageCORSRule
## SYNOPSIS
Removes CORS for a Storage service.

## SYNTAX

```
Remove-AzureStorageCORSRule [-ServiceType] [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-ServerTimeoutPerRequest <Int32]>]
```

## DESCRIPTION
The **Remove-AzureStorageCORSRule** cmdlet removes Cross-Origin Resource Sharing (CORS) for an azure_2 Storage service.
This cmdlet deletes all CORS rules in a Storage service type.
The types of storage services for this cmdlet are Blob, Table, Queue, and File.

## EXAMPLES

### Example 1: Remove CORS rules for the blob service
```
PS C:\>Remove-AzureStorageCORSRule -ServiceType Blob
```

This command removes CORS rules for the Blob service type.

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

### -Context
Specifies the azure_2 storage context.
To obtain the storage context, the New-AzureStorageContext cmdlet.

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

### -ServerTimeoutPerRequest
Specifies the length of the time-out period for the server part of a request.

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

### -ServiceType
Specifies the azure_2 Storage service type for which this cmdlet removes rules.
psdx_paramvalues

-- Blob 
-- Table 
-- Queue 
-- File

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Blob, Table, Queue, File

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageCORSRule](accfb0fd-ad3a-4415-abce-a98b8073e82b)

[Set-AzureStorageCORSRule](fd109b34-042a-4157-b0c1-2cbf29894b52)

