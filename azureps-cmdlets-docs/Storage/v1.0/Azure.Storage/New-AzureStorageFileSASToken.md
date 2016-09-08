---
external help file: RMAzure_Storage.xml
online version: 671aeec8-b7f9-49c5-866f-da84f189ab5b
schema: 2.0.0
---

# New-AzureStorageFileSASToken
## SYNOPSIS
Generates a shared access signature token for a Storage file.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
New-AzureStorageFileSASToken [-ShareName] <String> [-Path] <String> [-Context <AzureStorageContext>]
 [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>] [-Permission <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
```

### UNNAMED_PARAMETER_SET_2
```
New-AzureStorageFileSASToken [-ShareName] <String> [-Path] <String> [-Context <AzureStorageContext>]
 [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
 -Policy <String>
```

### UNNAMED_PARAMETER_SET_3
```
New-AzureStorageFileSASToken [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>]
 [-Permission <String>] [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>]
 [-StartTime <DateTime]>] -File <CloudFile>
```

### UNNAMED_PARAMETER_SET_4
```
New-AzureStorageFileSASToken [-ExpiryTime <DateTime]>] [-FullUri] [-IPAddressOrRange <String>]
 [-Protocol <Nullable [Microsoft.WindowsAzure.Storage.SharedAccessProtocol]>] [-StartTime <DateTime]>]
 -File <CloudFile> -Policy <String>
```

## DESCRIPTION
The **New-AzureStorageFileSASToken** cmdlet generates a shared access signature token for an azure_2 Storage file.

## EXAMPLES

### Example 1: Generate a shared access signature token that has full file permissions
```
PS C:\> New-AzureStorageFileSASToken -ShareName "ContosoShare" -Path "FilePath" -Permission "rwd"
```

This command generates a shared access signature token that has full permissions for the file that is named FilePath.

### Example 2: Generate a shared access signature token that has a time limit
```
PS C:\> $StartTime = Get-Date
PS C:\> $EndTime = $StartTime.AddHours(2.0)
PS C:\> New-AzureStorageFileSASToken -ShareName "ContosoShare" -Path "FilePath" -Permission "rwd" -StartTime $StartTime -ExpiryTime $EndTime
```

The first command creates a **DateTime** object by using the Get-Date cmdlet.
The command stores the current time in the $StartTime variable.

The second command adds two hours to the object in $StartTime, and then stores the result in the $EndTime variable.
This object is a time two hours in the future.

The third command generates a shared access signature token that has the specified permissions.
This token becomes valid at the current time.
The token remains valid until time stored in $EndTime.

## PARAMETERS

### -Context
Specifies an azure_2 Storage context.
To obtain a context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: AzureStorageContext
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -File
Specifies a **CloudFile** object.
You can create a cloud file or obtain one by using the Get-AzureStorageFile cmdlet.

```yaml
Type: CloudFile
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
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

### -Path
Specifies the path of the file relative to a Storage share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -Permission
Specifies the permissions for a Storage file.

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
Specifies the stored access policy for a file.

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

### -ShareName
Specifies the name of the Storage share.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
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

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[New-AzureStorageShareSASToken](07c8ad4e-7a32-4407-9120-1432126b7376)

