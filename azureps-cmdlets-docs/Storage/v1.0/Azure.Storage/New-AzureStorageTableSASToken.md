---
external help file: RMAzure_Storage.xml
online version: 671aeec8-b7f9-49c5-866f-da84f189ab5b
schema: 2.0.0
---

# New-AzureStorageTableSASToken
## SYNOPSIS
Generates an SAS token for an azure_2 Storage table.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureStorageTableSASToken [-Name] <String> [-Context <AzureStorageContext>] [-EndPartitionKey <String>]
 [-EndRowKey <String>] [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartPartitionKey <String>]
 [-StartRowKey <String>] [-StartTime <DateTime]>] -Policy <String>
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureStorageTableSASToken [-Name] <String> [-Context <AzureStorageContext>] [-EndPartitionKey <String>]
 [-EndRowKey <String>] [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>] [-Permission <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartPartitionKey <String>]
 [-StartRowKey <String>] [-StartTime <DateTime]>]
```

## DESCRIPTION
The **New-AzureStorageTableSASToken** cmdlet generates a Shared Access Signature (SAS) token for an azure_2 Storage table.

## EXAMPLES

### Example 1: Generate an SAS token that has full permissions for a table
```
C:\PS>New-AzureStorageTableSASToken -Name "ContosoResources" -Permission "raud"
```

This command generates an SAS token with full permissions for the table named ContosoResources.
That token is for read, add, update, and delete permissions.

### Example 2: Generate an SAS token for a range of partitions
```
C:\PS>New-AzureStorageTableSASToken -Name "ContosoResources" -Permission "raud" -StartPartitionKey "a" -EndPartitionKey "b"
```

This command generates and SAS token with full permissions for the table named ContosoResources.
The command limits the token to the range that the *StartPartitionKey* and *EndPartitionKey* parameters specify.

### Example 3: Generate an SAS token that has a stored access policy for a table
```
C:\PS>New-AzureStorageTableSASToken -Name "ContosoResources" -Policy "ClientPolicy01"
```

This command generates an SAS token for the table named ContosoResources.
The command specifies the stored access policy named ClientPolicy01.

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

### -EndPartitionKey
Specifies the partition key of the end of the range for the token that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: endpk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndRowKey
Specifies the row key for the end of the range for the token that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: endrk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryTime
Specifies when the SAS token expires.

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

### -FullUri
Indicates that this cmdlet returns the full queue URI with the SAS token.

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

### -IPAddressOrRange
@{Text=}

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

### -Name
Specifies the name of an azure_2 Storage table.
This cmdlet creates an SAS token for the table that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N,Table

Required: True
Position: 1
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -Permission
Specifies permissions for an azure_2 Storage table.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
@{Text=}

```yaml
Type: Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartPartitionKey
Specifies the partition key of the start of the range for the token that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: startpk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartRowKey
Specifies the row key for the start of the range for the token that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: startrk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies when the SAS token becomes valid.

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

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

