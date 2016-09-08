---
external help file: RMAzure_Storage.xml
online version: f5420030-d139-44d7-847b-86ae910b98cd
schema: 2.0.0
---

# New-AzureStorageQueueStoredAccessPolicy
## SYNOPSIS
Creates a stored access policy for an azure_2 storage queue.

## SYNTAX

```
New-AzureStorageQueueStoredAccessPolicy [-Queue] <String> [-Policy] <String> [-Context <AzureStorageContext>]
 [-ExpiryTime <DateTime]>] [-Permission <String>] [-StartTime <DateTime]>]
```

## DESCRIPTION
The **New-AzureStorageQueueStoredAccessPolicy** cmdlet creates a stored access policy for an azure_2 storage queue.

## EXAMPLES

### Example 1: Create a stored access policy in a storage queue
```
PS C:\>New-AzureStorageQueueStoredAccessPolicy -Queue "MyQueue" -Policy "Policy01"
```

This command creates an access policy named Policy01 in the storage queue named MyQueue.

## PARAMETERS

### -Context
Specifies an azure_2 storage context.
To obtain a storage context, use the New-AzureStorageContext cmdlet.

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

### -ExpiryTime
Specifies the time at which the stored access policy becomes invalid.

```yaml
Type: DateTime]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Permission
Specifies the level of public access to this storage queue.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies a stored access policy, which includes the permissions for this SAS token.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Queue
Specifies the azure_2 storage queue name.

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

### -StartTime
Specifies the time at which the stored access policy becomes valid.

```yaml
Type: DateTime]
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

[Get-AzureStorageQueueStoredAccessPolicy](f5420030-d139-44d7-847b-86ae910b98cd)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[Remove-AzureStorageQueueStoredAccessPolicy](8d80d1be-2e66-4372-9d51-2afff62d011d)

[Set-AzureStorageQueueStoredAccessPolicy](02396020-02c8-4736-a00e-8d7112e27286)

