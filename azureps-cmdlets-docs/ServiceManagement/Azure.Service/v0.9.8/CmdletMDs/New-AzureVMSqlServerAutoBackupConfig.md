---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\New-AzureVMSqlServerAutoPatchingConfig.md
schema: 2.0.0
---

# New-AzureVMSqlServerAutoBackupConfig

## SYNOPSIS
Creates a configuration object for SQL Server automatic backup.

## SYNTAX

### StorageUriSqlServerAutoBackup (Default)
```
New-AzureVMSqlServerAutoBackupConfig [-Enable] [-RetentionPeriodInDays <Int32>] [-EnableEncryption]
 [[-CertificatePassword] <SecureString>] [-StorageUri <Uri>] [-StorageKey <SecureString>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### StorageContextSqlServerAutoBackup
```
New-AzureVMSqlServerAutoBackupConfig [-Enable] [-RetentionPeriodInDays <Int32>] [-EnableEncryption]
 [[-CertificatePassword] <SecureString>] [[-StorageContext] <AzureStorageContext>] [-StorageUri <Uri>]
 [-StorageKey <SecureString>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVMSqlServerAutoBackupConfig** cmdlet creates a configuration object for SQL Server automatic backup.

## EXAMPLES

### Example 1: Create an auto-backup configuration using storage URI and account key
```
PS C:\>$ABS = New-AzureVMSqlServerAutoBackupConfig -Enable -RetentionPeriod 10 -StorageUri $StorageUrl -StorageKey $StorageAccountKeySecure
Enable                : True
EnableEncryption      : False
RetentionPeriodInDays : 10
```

This command creates an auto-backup configuration object by specifying storage URL and account key.

### Example 2: Create an auto-backup configuration using storage context
```
PS C:\>$ABS = New-AzureVMSqlServerAutoBackupConfig -StorageContext $StorageContext -Enable -RetentionPeriod 10
Enable                : True
EnableEncryption      : False
RetentionPeriodInDays : 10
```

This command creates an auto-backup configuration object by specifying storage context.

### Example 3: Create an auto-backup configuration using storage context with encryption and password
```
PS C:\>$ABS = New-AzureVMSqlServerAutoBackupConfig -StorageContext $StorageContext -Enable -RetentionPeriod 10 -EnableEncryption -CertificatePassword $CertPasswd
Enable                : True
EnableEncryption      : True
RetentionPeriodInDays : 10
```

This command creates an auto-backup configuration object by specifying Storage context and enabling encryption option with password.
The certificatepassword ist stored in the variable named $CertPasswd.

## PARAMETERS

### -Enable
Indicates that automated backup for the SQL Server virtual machine is enabled.
If you use this parameter, automated backup sets a backup schedule for all current and new databases.
This updates your Managed Backup settings to follow this schedule.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificatePassword
Specifies a password to encrypt the certificate that is used to perform SQL Server encrypted backups.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContext
Specifies the storage account to be used to store backups.
Default is the storage account associated with the SQL Server virtual machine.

```yaml
Type: AzureStorageContext
Parameter Sets: StorageContextSqlServerAutoBackup
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableEncryption
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionPeriodInDays
```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageKey
Specifies the storage key of the blob storage account.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageUri
Specifies a URI to the blob storage account.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureVMSqlServerAutoPatchingConfig](.\New-AzureVMSqlServerAutoPatchingConfig.md)

