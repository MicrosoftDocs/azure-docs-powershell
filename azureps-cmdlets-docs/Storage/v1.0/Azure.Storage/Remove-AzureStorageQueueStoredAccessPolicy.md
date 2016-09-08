---
external help file: RMAzure_Storage.xml
online version: f5420030-d139-44d7-847b-86ae910b98cd
schema: 2.0.0
---

# Remove-AzureStorageQueueStoredAccessPolicy
## SYNOPSIS
Removes a stored access policy from an azure_2 storage queue.

## SYNTAX

```
Remove-AzureStorageQueueStoredAccessPolicy [-Queue] <String> [-Policy] <String>
 [-Context <AzureStorageContext>] [-Force] [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-AzureStorageQueueStoredAccessPolicy** cmdlet removes a stored access policy from an azure_2 storage queue.

## EXAMPLES

### Example 1: Remove a stored access policy from a storage queue
```
PS C:\>Remove-AzureStorageQueueStoredAccessPolicy -Queue "MyQueue" -Policy "Policy04"
```

This command removes an access policy named Policy04 from the storage queue named MyQueue.

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

### -Policy
Specifies the stored access policy, which includes the permissions for this Shared Access Signature (SAS) token.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
Accept pipeline input: True(ByPropertyName)
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

[Get-AzureStorageQueueStoredAccessPolicy](f5420030-d139-44d7-847b-86ae910b98cd)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[New-AzureStorageQueueStoredAccessPolicy](64a4e0c7-905e-406b-afb7-1723afcee9e8)

[Set-AzureStorageQueueStoredAccessPolicy](02396020-02c8-4736-a00e-8d7112e27286)

