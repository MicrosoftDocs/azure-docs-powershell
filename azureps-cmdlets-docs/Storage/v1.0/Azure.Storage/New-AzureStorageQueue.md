---
external help file: RMAzure_Storage.xml
online version: a89aa1b2-cabd-4048-a84d-2b37da287c05
schema: 2.0.0
---

# New-AzureStorageQueue
## SYNOPSIS
Creates a storage queue.

## SYNTAX

```
New-AzureStorageQueue [-Name] <String> [-Context <AzureStorageContext>]
```

## DESCRIPTION
The **New-AzureStorageQueue** cmdlet creates a storage queue in azure_2.

## EXAMPLES

### Example 1: Create an Azure storage queue
```
PS C:\>New-AzureStorageQueue -Name "queueabc"
```

This example creates a storage queue named queueabc.

### Example 2: Create multiple azure storage queues
```
PS C:\>"queue1 queue2 queue3".split() | New-AzureStorageQueue
```

This example creates multiple storage queues.
It uses the Split method of the .NET String class and then passes the names on the pipeline.

## PARAMETERS

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
Specifies a name for the queue.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Queue

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageQueue](a89aa1b2-cabd-4048-a84d-2b37da287c05)

[Remove-AzureStorageQueue](265824d1-e3d4-4bd4-bc11-466c2100ed3a)

