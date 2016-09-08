---
external help file: RMAzure_Storage.xml
online version: 4880a1a4-c947-4310-8317-0a837b8acb7f
schema: 2.0.0
---

# Remove-AzureStorageContainer
## SYNOPSIS
Removes the specified storage container.

## SYNTAX

```
Remove-AzureStorageContainer [-Name] <String> [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-Force] [-PassThru]
 [-ServerTimeoutPerRequest <Int32]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureStorageContainer** cmdlet removes the specified storage container in azure_2.

## EXAMPLES

### Example 1: Remove a container
```
PS C:\>Remove-AzureStorageContainer â€"Name "MyTestContainer"
```

This example removes a container named MyTestContainer.

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
Specifies a context for the container you want to remove.
You can use the New-AzureStorageContext cmdlet to create it.

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
ps_force

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

### -Name
Specifies the name of the container to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Container

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns a **Boolean** that reflects the success of the operation.
By default, this cmdlet does not return a value.

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

[Get-AzureStorageContainer](4880a1a4-c947-4310-8317-0a837b8acb7f)

[New-AzureStorageContainer](f3da4bf0-aa3a-4853-a362-e3fc479688d6)

