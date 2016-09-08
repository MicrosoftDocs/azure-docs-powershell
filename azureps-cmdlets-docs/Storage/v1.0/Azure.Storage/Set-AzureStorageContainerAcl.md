---
external help file: RMAzure_Storage.xml
online version: 4880a1a4-c947-4310-8317-0a837b8acb7f
schema: 2.0.0
---

# Set-AzureStorageContainerAcl
## SYNOPSIS
Sets the public access permission to a storage container.

## SYNTAX

```
Set-AzureStorageContainerAcl [-Name] <String> [-Permission] [-ClientTimeoutPerRequest <Int32]>]
 [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>] [-PassThru]
 [-ServerTimeoutPerRequest <Int32]>]
```

## DESCRIPTION
The **Set-AzureStorageContainerAcl** cmdlet sets the public access permission to the specified storage container in azure_2.

## EXAMPLES

### Example 1: Set azure storage container ACL by name
```
PS C:\>Set-AzureStorageContainerAcl -Container "Container01" -Permission Off -PassThru
```

This command creates a container that has no public access.

### Example 2: Set azure storage container ACL by using the pipeline
```
PS C:\>Get-AzureStorageContainer container* | Set-AzureStorageContainerAcl -Permission Blob -PassThru
```

This command gets all storage containers whose name starts with container and then passes the result on the pipeline to set the permission for them all to Blob access.

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
You can create it by using the New-AzureStorageContext cmdlet.

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
Specifies a container name.

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
passthru

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
Specifies the level of public access to this container.
By default, the container and any blobs in it can be accessed only by the owner of the storage account.
To grant anonymous users read permissions to a container and its blobs, you can set the container permissions to enable public access.
Anonymous users can read blobs in a publicly available container without authenticating the request.
psdx_paramvalues

--Container.
Provides full read access to a container and its blobs.
Clients can enumerate blobs in the container through anonymous request, but cannot enumerate containers in the storage account. 
--Blob.
Provides read access to blob data in a container through anonymous request, but does not provide access to container data.
Clients cannot enumerate blobs in the container by using anonymous request. 
--Off.
Restricts access to only the storage account owner.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: PublicAccess
Accepted values: Off, Container, Blob

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Specifies the service side time-out interval, in seconds, for a request.
If the specified interval elapses before the service processes the request, the storage service returns an error.
Server side time out for each request.

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

[Get-AzureStorageContainer](4880a1a4-c947-4310-8317-0a837b8acb7f)

[New-AzureStorageContainer](f3da4bf0-aa3a-4853-a362-e3fc479688d6)

[Remove-AzureStorageContainer](89d7ed7c-1db6-4e01-8981-8f34483039fd)

