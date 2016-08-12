---
external help file: RMAzure_Storage.xml
online version: 10a13c83-d545-4729-99f9-048c774f32d7
schema: 2.0.0
---

# New-AzureStorageShareSASToken
## SYNOPSIS
Generate Shared Access Signature token for azure_2 Storage share.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureStorageShareSASToken [-ShareName] <String> [-Context <AzureStorageContext>] [-ExpiryTime <DateTime]>]
 [-FullUri] [-IPAddressOrRange <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
 -Policy <String>
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureStorageShareSASToken [-ShareName] <String> [-Context <AzureStorageContext>] [-ExpiryTime <DateTime]>]
 [-FullUri] [-IPAddressOrRange <String>] [-Permission <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
```

## DESCRIPTION
The **New-AzureStorageShareSASToken** cmdlet generates a shared access signature token for an azure_2 Storage share.

## EXAMPLES

### Example 1: Generate a shared access signature token for a share
```
PS C:\>New-AzureStorageShareSASToken -ShareName "ContosoShare" -Permission "rwdl"
```

This command creates a shared access signature token for the share named ContosoShare.

### Example 2: Generate multiple shared access signature token by using the pipeline
```
PS C:\>Get-AzureStorageShare -Prefix "test" | New-AzureStorageShareSASToken -Permission "rwdl"
```

This command gets all the Storage shares that match the prefix test.
The command passes them to the current cmdlet by using the pipeline operator.
The current cmdlet creates a shared access token for each Storage share that has the specified permissions.

### Example 3: Generate a shared access signature token that uses a shared access policy
```
PS C:\>New-AzureStorageShareSASToken -ShareName "ContosoShare" -Policy "ContosoPolicy03"
```

This command creates a shared access signature token for the Storage share named ContosoShare that has the policy named ContosoPolicy03.

## PARAMETERS

### -Context
Specifies an azure_2 Storage context.
To obtain a context, use the New-AzureStorageContext cmdlet.

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

### -Permission
Specifies the permissions in the token to access the share and files under the share.

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
Specifies the stored access policy for a share.

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

### -ShareName
Specifies the name of the Storage share.

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
Keywords: common, azure, services, data, storage, blob, queue, table

## RELATED LINKS

[Get-AzureStorageShare](10a13c83-d545-4729-99f9-048c774f32d7)

[New-AzureStorageFileSASToken](4fb064f5-94bc-4d8f-9ef6-2611f8aab99c)

