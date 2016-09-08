---
external help file: RMAzure_Storage.xml
online version: 4880a1a4-c947-4310-8317-0a837b8acb7f
schema: 2.0.0
---

# New-AzureStorageContainer
## SYNOPSIS
Creates an azure_2 storage container.

## SYNTAX

```
New-AzureStorageContainer [-Name] <String> [[-Permission] <BlobContainerPublicAccessType]>]
 [-ClientTimeoutPerRequest <Int32]>] [-ConcurrentTaskCount <Int32]>] [-Context <AzureStorageContext>]
 [-ServerTimeoutPerRequest <Int32]>]
```

## DESCRIPTION
The **New-AzureStorageContainer** cmdlet creates an azure_2 storage container.

## EXAMPLES

### Example 1: Create an Azure storage container
```
PS C:\>New-AzureStorageContainer -Name "ContainerName" -Permission Off
```

This command creates a storage container.

### Example 2: Create multiple Azure storage containers
```
PS C:\>"container1 container2 container3".split() | New-AzureStorageContainer -Permission Container
```

This example creates multiple storage containers.
It uses the **Split** method of the .NET **String** class and then passes the names on the pipeline.

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
Specifies a context for the new container.

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
Specifies a name for the new container.

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

### -Permission
Specifies the level of public access to this container.
By default, the container and any blobs in it can be accessed only by the owner of the storage account.
To grant anonymous users read permissions to a container and its blobs, you can set the container permissions to enable public access.
Anonymous users can read blobs in a publicly available container without authenticating the request.
psdx_paramvalues

-- Container.
Provides full read access to a container and its blobs.
Clients can enumerate blobs in the container through anonymous request, but cannot enumerate containers in the storage account. 
-- Blob.
Provides read access to blob data throughout a container through anonymous request, but does not provide access to container data.
Clients cannot enumerate blobs in the container by using anonymous request. 
-- Off.
Which restricts access to only the storage account owner.

```yaml
Type: BlobContainerPublicAccessType]
Parameter Sets: (All)
Aliases: PublicAccess

Required: False
Position: 2
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

[Get-AzureStorageContainer](4880a1a4-c947-4310-8317-0a837b8acb7f)

[Remove-AzureStorageContainer](89d7ed7c-1db6-4e01-8981-8f34483039fd)

[Set-AzureStorageContainerAcl](20680af5-8145-4eab-94d3-d710a62a062b)

