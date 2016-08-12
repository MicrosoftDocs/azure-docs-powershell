---
external help file: RMAzure_Storage.xml
online version: 64a4e0c7-905e-406b-afb7-1723afcee9e8
schema: 2.0.0
---

# Get-AzureStorageQueueStoredAccessPolicy
## SYNOPSIS
Gets the stored access policy or policies for an azure_2 storage queue.

## SYNTAX

```
Get-AzureStorageQueueStoredAccessPolicy [-Queue] <String> [[-Policy] <String>] [-Context <AzureStorageContext>]
```

## DESCRIPTION
The **Get-AzureStorageQueueStoredAccessPolicy** cmdlet lists the stored access policy or policies for an azure_2 storage queue.

## EXAMPLES

### Example 1: Get a stored access policy in the queue
```
PS C:\>Get-AzureStorageQueueStoredAccessPolicy -Queue "MyQueue" -Policy "Policy12"
```

This command gets the access policy named Policy12 in the storage queue named MyQueue.

### Example 2: Get all stored access policies in the queue
```
PS C:\>Get-AzureStorageQueueStoredAccessPolicy -Queue "MyQueue"
```

This command gets all stored access policies in the queue named MyQueue.

## PARAMETERS

### -Context
Specifies the azure_2 storage context.
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

### -Policy
Specifies a stored access policy, which includes the permissions for this Shared Access Signature (SAS) token.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageQueueStoredAccessPolicy](64a4e0c7-905e-406b-afb7-1723afcee9e8)

[Remove-AzureStorageQueueStoredAccessPolicy](8d80d1be-2e66-4372-9d51-2afff62d011d)

[Set-AzureStorageQueueStoredAccessPolicy](02396020-02c8-4736-a00e-8d7112e27286)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

