---
external help file: SMAzure_Compute.xml
online version: http://go.microsoft.com/FWLink/p/?LinkID=311700
schema: 2.0.0
---

# Disable-AzureWebsiteApplicationDiagnostic
## SYNOPSIS
Disables application diagnostics for an Azure website.

## SYNTAX

```
Disable-AzureWebsiteApplicationDiagnostic [[-Name] <String>] [-File] [-PassThru] [-Slot <String>] [-Storage]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

Disables application diagnostics for an Azure website.
Disables logging configured to be stored on a file system or on Azure.

## EXAMPLES

### 1:  Disable application logging file
```
C:\PS>Disable-AzureWebsiteApplicationDiagnostic -Name MyWebsite -File
```

The following example disables application logging on the file system.

### 2:  Disable logging using Azure storage
```
C:\PS>Disable-AzureWebsiteApplicationDiagnostic -Name MyWebsite -Storage
```

The following example disables application logging using storage.

## PARAMETERS

### -File
Specifies that you want to use the file system to store the log files.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the website.

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
Flag to return true if succeeded

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
Indicates using Azure Storage to store the log files.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AzureWebsiteApplicationDiagnostic](5e0e5009-a69f-4621-a317-68a8109aabf8)

[Get-AzureWebsite](0c2a5092-db45-4ce7-b39b-d1e499b4a867)

[New-AzureWebsite](498c1abd-298b-43e9-ac53-bc57054a5387)

[Remove-AzureWebsite](3997c3b8-37ce-4135-a17d-63ae3bdd8e74)

[Start-AzureWebsite](d6ee400f-4a92-4f2f-83bb-70188bb2000d)

