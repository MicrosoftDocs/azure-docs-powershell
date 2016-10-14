---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: http://go.microsoft.com/FWLink/p/?LinkID=311701
schema: 2.0.0
---

# Enable-AzureWebsiteApplicationDiagnostic

## SYNOPSIS
Enables application diagnostics on an Azure website.

## SYNTAX

### FileParameterSet
```
Enable-AzureWebsiteApplicationDiagnostic [-PassThru] [-File] [-LogLevel] <LogEntryType> [[-Name] <String>]
 [[-Slot] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### TableStorageParameterSet
```
Enable-AzureWebsiteApplicationDiagnostic [-PassThru] [-TableStorage] [-LogLevel] <LogEntryType>
 [[-StorageAccountName] <String>] [-StorageTableName <String>] [[-Name] <String>] [[-Slot] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### BlobStorageParameterSet
```
Enable-AzureWebsiteApplicationDiagnostic [-PassThru] [-BlobStorage] [-LogLevel] <LogEntryType>
 [[-StorageAccountName] <String>] [-StorageBlobContainerName <String>] [[-Name] <String>] [[-Slot] <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

Enables application diagnostics on an Azure website, and allows you to configure storage of logs on a file system or on Azure storage.

## EXAMPLES

### 1: Enable diagnostics using file system
```
C:\PS>Enable-AzureWebsiteApplicationDiagnostic -Name MyWebsite -File -LogLevel Verbose
```

This example enables application logging on file system with verbose level.

### 2: Enable logging using Azure Storage
```
C:\PS>Enable-AzureWebsiteApplicationDiagnostic -Name MyWebsite -Storage -LogLevel Information -StorageAccountName myaccount
```

This example enables application logging using storage account named  ¢â‚¬Å"myaccount ¢â‚¬Â with logging level set to  ¢â‚¬Å"information ¢â‚¬Â.

## PARAMETERS

### -Name
The name of the Azure website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -File
Specifies that you want to use a file system to store the log files.

```yaml
Type: SwitchParameter
Parameter Sets: FileParameterSet
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
The storage account to use for storing the logs.
If not specified, the CurrentStorageAccount is used.

```yaml
Type: String
Parameter Sets: TableStorageParameterSet, BlobStorageParameterSet
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogLevel
The log level to store.

```yaml
Type: LogEntryType
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Flag to return true if the command succeeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Specifies the name of slot.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BlobStorage
{{Fill BlobStorage Description}}

```yaml
Type: SwitchParameter
Parameter Sets: BlobStorageParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageBlobContainerName
{{Fill StorageBlobContainerName Description}}

```yaml
Type: String
Parameter Sets: BlobStorageParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTableName
{{Fill StorageTableName Description}}

```yaml
Type: String
Parameter Sets: TableStorageParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TableStorage
{{Fill TableStorage Description}}

```yaml
Type: SwitchParameter
Parameter Sets: TableStorageParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AzureWebsiteApplicationDiagnostic](.\Disable-AzureWebsiteApplicationDiagnostic.md)

[Get-AzureWebsite](.\Get-AzureWebsite.md)

[New-AzureWebsite](.\New-AzureWebsite.md)

[Remove-AzureWebsite](.\Remove-AzureWebsite.md)

[Start-AzureWebsite](.\Start-AzureWebsite.md)

