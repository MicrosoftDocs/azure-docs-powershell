---
external help file: RMAzure_Storage.xml
online version: f5420030-d139-44d7-847b-86ae910b98cd
schema: 2.0.0
---

# Set-AzureStorageQueueStoredAccessPolicy
## SYNOPSIS
Sets a stored access policy for an azure_2 storage queue.

## SYNTAX

```
Set-AzureStorageQueueStoredAccessPolicy [-Queue] <String> [-Policy] <String> [-Context <AzureStorageContext>]
 [-ExpiryTime <DateTime]>] [-NoExpiryTime] [-NoStartTime] [-Permission <String>] [-StartTime <DateTime]>]
```

## DESCRIPTION
The **Set-AzureStorageQueueStoredAccessPolicy** cmdlet sets a stored access policy for an azure_2 storage queue.

## EXAMPLES

### Example 1: Set a stored access policy in the queue
```
PS C:\> Set-AzureStorageQueueStoredAccessPolicy -Queue "MyQueue" -Policy "Policy07"
```

This command sets an access policy named Policy07 for storage queue named MyQueue.

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

### -NoExpiryTime
Indicates that the access policy has no expiration date.

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

### -NoStartTime
Indicates that this cmdlet sets the start time to be $Null.

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

[New-AzureStorageQueueStoredAccessPolicy](64a4e0c7-905e-406b-afb7-1723afcee9e8)

[Remove-AzureStorageQueueStoredAccessPolicy](8d80d1be-2e66-4372-9d51-2afff62d011d)

