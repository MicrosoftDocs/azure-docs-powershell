---
external help file: RMAzure_Storage.xml
online version: f08d2de2-a276-439c-b9a8-ee187a8c334e
schema: 2.0.0
---

# New-AzureStorageContainerSASToken
## SYNOPSIS
Generates an SAS token for an azure_2 storage container.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureStorageContainerSASToken [-Name] <String> [-Context <AzureStorageContext>] [-ExpiryTime <DateTime]>]
 [-FullUri] [-IPAddressOrRange <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
 -Policy <String>
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureStorageContainerSASToken [-Name] <String> [-Context <AzureStorageContext>] [-ExpiryTime <DateTime]>]
 [-FullUri] [-IPAddressOrRange <String>] [-Permission <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
```

## DESCRIPTION
The **New-AzureStorageContainerSASToken** cmdlet generates a Shared Access Signature (SAS) token for an azure_2 storage container.

## EXAMPLES

### Example 1: Generate a container SAS token with full container permission
```
PS C:\>New-AzureStorageContainerSASToken -Name "Test" -Permission rwdl
```

This example generates a container SAS token with full container permission.

### Example 2: Generate multiple container SAS token by pipeline
```
PS C:\>Get-AzureStorageContainer -Container test* | New-AzureStorageContainerSASToken -Permission rwdl
```

This example generates multiple container SAS tokens by using the pipeline.

### Example 3: Generate container SAS token with shared access policy
```
PS C:\>New-AzureStorageContainerSASToken -Name "Test" -Policy "PolicyName"
```

This example generates a container SAS token with shared access policy.

## PARAMETERS

### -Context
Specifies an azure_2 storage context.
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

### -ExpiryTime
Specifies the time at which the shared access signature becomes invalid.

If the user sets the start time but not the expiry time, the expiry time is set to the start time plus one hour.
If neither the start time nor the expiry time is specified, the expiry time is set to the current time plus one hour.

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
Indicates that this cmdlet return the full blob URI and the shared access signature token.

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
Specifies an azure_2 storage container name.

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
Specifies permissions for a storage container.

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
Specifies an azure_2 Stored Access Policy.

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

### -StartTime
Specifies the time at which the shared access signature becomes valid.

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

[New-AzureStorageBlobSASToken](f08d2de2-a276-439c-b9a8-ee187a8c334e)

