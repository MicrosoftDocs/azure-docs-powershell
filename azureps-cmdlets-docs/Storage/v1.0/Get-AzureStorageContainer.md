---
external help file: RMAzure_Storage.xml
online version: f3da4bf0-aa3a-4853-a362-e3fc479688d6
schema: 2.0.0
---

# Get-AzureStorageContainer
## SYNOPSIS
Lists the storage containers.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageContainer [[-Name] <String>] [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-ContinuationToken <BlobContinuationToken>]
 [-MaxCount <Int32]>] [-ServerTimeoutPerRequest <Int32]>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageContainer [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>]
 [-Context <AzureStorageContext>] [-ContinuationToken <BlobContinuationToken>] [-MaxCount <Int32]>]
 [-ServerTimeoutPerRequest <Int32]>] -Prefix <String>
```

## DESCRIPTION
The **Get-AzureStorageContainer** cmdlet lists the storage containers associated with the storage account in azure_2.

## EXAMPLES

### Example 1: Get Azure Storage blob by name
```
PS C:\>Get-AzureStorageContainer -Name container*
```

This example uses a wildcard character to return a list of all containers with a name that starts with container.

### Example 2: Get Azure Storage container by container name prefix
```
PS C:\>Get-AzureStorageContainer -Prefix "container"
```

This example uses the *Prefix* parameter to return a list of all containers with a name that starts with container.

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
Specifies the storage context.
To create it, you can use the New-AzureStorageContext cmdlet.

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

### -ContinuationToken
Specifies a continuation token for the blob list.

```yaml
Type: BlobContinuationToken
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCount
Specifies the maximum number of objects that this cmdlet returns.

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

### -Name
Specifies the container name.
If container name is empty, the cmdlet lists all the containers.
Otherwise, it lists all containers that match the specified name or the regular name pattern.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: N,Container

Required: False
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Prefix
Specifies a prefix used in the name of the container or containers you want to get.
You can use this to find all containers that start with the same string, such as "my" or "test".

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

[New-AzureStorageContainer](f3da4bf0-aa3a-4853-a362-e3fc479688d6)

[Remove-AzureStorageContainer](89d7ed7c-1db6-4e01-8981-8f34483039fd)

[Set-AzureStorageContainerAcl](20680af5-8145-4eab-94d3-d710a62a062b)

