---
external help file: SMAzure_Compute.xml
online version: http://go.microsoft.com/FWLink/p/?LinkID=311701
schema: 2.0.0
---

# Enable-AzureWebsiteApplicationDiagnostic
## SYNOPSIS
Enables application diagnostics on an Azure website.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Enable-AzureWebsiteApplicationDiagnostic [[-Name] <String>] [-PassThru] [-Slot <String>] [-File] [-LogLevel]
```

### UNNAMED_PARAMETER_SET_2
```
Enable-AzureWebsiteApplicationDiagnostic [[-Name] <String>] [-PassThru] [-Slot <String>]
 [-StorageAccountName <String>] [-LogLevel] [-Storage]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

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

This example enables application logging using storage account named â€œmyaccountâ€ with logging level set to â€œinformationâ€.

## PARAMETERS

### -File
Specifies that you want to use a file system to store the log files.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogLevel
The log level to store.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Error, Warning, Information, Verbose

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the Azure website.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Flag to return true if the command succeeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
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
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Storage
Specifies that you want to use Azure to store the log files.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
The storage account to use for storing the logs.
If not specified, the CurrentStorageAccount is used.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-AzureWebsiteApplicationDiagnostic](40b3665f-ec67-4ee7-9349-d16c0b2e2495)

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

[Start-AzureWebsite](d6ee400f-4a92-4f2f-83bb-70188bb2000d)

