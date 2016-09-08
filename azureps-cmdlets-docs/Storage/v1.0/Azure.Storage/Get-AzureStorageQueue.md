---
external help file: RMAzure_Storage.xml
online version: 4b1216b7-40c6-418b-806e-63302d8ba4a1
schema: 2.0.0
---

# Get-AzureStorageQueue
## SYNOPSIS
Lists storage queues.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-AzureStorageQueue [[-Name] <String>] [-Context <AzureStorageContext>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-AzureStorageQueue [-Context <AzureStorageContext>] -Prefix <String>
```

## DESCRIPTION
The **Get-AzureStorageQueue** cmdlet lists storage queues associated with an azure_2 Storage account.

## EXAMPLES

### Example 1: List all Azure Storage queues
```
PS C:\>Get-AzureStorageQueue
```

This command gets a list of all storage queues for the current Storage account.

### Example 2: List Azure Storage queues using a wildcard character
```
PS C:\>Get-AzureStorageQueue -Name queue*
```

This command uses a wildcard character to get a list of storage queues whose name starts with queue.

### Example 3: List Azure Storage queues using queue name prefix
```
PS C:\>Get-AzureStorageQueue -Prefix "queue"
```

This example uses the *Prefix* parameter to get a list of storage queues whose name starts with queue.

## PARAMETERS

### -Context
Specifies the azure_2 storage context.
You can create it by using the **New-AzureStorageContext** cmdlet.

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
Specifies a name.
If no name is specified, the cmdlet gets a list of all the queues.
If a full or partial name is specified, the cmdlet gets all queues that match the name pattern.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: N,Queue

Required: False
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Prefix
Specifies a prefix used in the name of the queues you want to get.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageQueue](4b1216b7-40c6-418b-806e-63302d8ba4a1)

[Remove-AzureStorageQueue](265824d1-e3d4-4bd4-bc11-466c2100ed3a)

