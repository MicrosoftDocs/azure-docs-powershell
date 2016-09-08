---
external help file: RMAzure_Storage.xml
online version: 74bc4494-be41-4493-9939-e51e61dd09e6
schema: 2.0.0
---

# New-AzureStorageBlobSASToken
## SYNOPSIS
Generates an SAS token for an azure_2 storage blob.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureStorageBlobSASToken [-Container] <String> [-Blob] <String> [-Context <AzureStorageContext>]
 [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>] [-Permission <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureStorageBlobSASToken [-Container] <String> [-Blob] <String> [-Context <AzureStorageContext>]
 [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
 -Policy <String>
```

### UNNAMED_PARAMETER_SET_3
```
New-AzureStorageBlobSASToken [-Context <AzureStorageContext>] [-ExpiryTime <DateTime]>] [-FullUri]
 [-IPAddressOrRange <String>] [-Permission <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
 -CloudBlob <CloudBlob>
```

### UNNAMED_PARAMETER_SET_4
```
New-AzureStorageBlobSASToken [-Context <AzureStorageContext>] [-ExpiryTime <DateTime]>] [-FullUri]
 [-IPAddressOrRange <String>] [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>]
 [-StartTime <DateTime]>] -CloudBlob <CloudBlob> -Policy <String>
```

## DESCRIPTION
The **New-AzureStorageBlobSASToken** cmdlet generates a Shared Access Signature (SAS) token for an azure_2 storage blob.

## EXAMPLES

### Example 1: Generate a blob SAS token with full blob permission
```
PS C:\>New-AzureStorageBlobSASToken -Container "ContainerName" -Blob "BlobName" -Permission rwd
```

This example generates a blob SAS token with full blob permission.

### Example 2: Generate a blob SAS token with life time
```
PS C:\> $StartTime = Get-Date
PS C:\> $EndTime = $startTime.AddHours(2.0)
PS C:\> New-AzureStorageBlobSASToken -Container "ContainerName" -Blob "BlobName" -Permission rwd -StartTime $StartTime -ExpiryTime $EndTime
```

This example generates a blob SAS token with life time.

## PARAMETERS

### -Blob
Specifies the storage blob name.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudBlob
Specifies the **CloudBlob** object.
To obtain a **CloudBlob** object, use the Get-AzureStorageBlob cmdlet.

```yaml
Type: CloudBlob
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: ICloudBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByPropertyName)
Accept wildcard characters: False
```

### -Container
Specifies the storage container name.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Specifies the storage context.

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
Specifies when the shared access signature expires.

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
Specifies the permissions for a storage blob.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_3
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
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_4
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

[Get-AzureStorageBlob](74bc4494-be41-4493-9939-e51e61dd09e6)

[New-AzureStorageContainerSASToken](dc3564e2-9ede-4901-8d62-f49017a03281)

