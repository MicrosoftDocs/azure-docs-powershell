---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Storage.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Storage
ms.date: 11/12/2026
PlatyPS schema version: 2024-05-01
title: New-AzStorageDirectory
---

# New-AzStorageDirectory

## SYNOPSIS

Creates a directory in a file share.

## SYNTAX

### Default (Default)

```
New-AzStorageDirectory [-Url <string>] [-StorageAccountName <string>] [-ShareName <string>]
 [-DirectoryPath <string>] [-StorageAccountKey <string>] [-SasToken <string>] [-Metadata <string[]>]
 [-Timeout <int>] [-ClientRequestId <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Creates a directory in a file share. Nested paths such as parent/child are supported, but the parent directory must already exist. Authenticate with -StorageAccountName and -StorageAccountKey, or with -SasToken. Alternatively, pass the full resource URL with -Url.

## EXAMPLES

### Example 1: Create a directory

```powershell
New-AzStorageDirectory -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare -DirectoryPath mydir
```

### Example 2: Create a nested directory

```powershell
New-AzStorageDirectory -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare -DirectoryPath mydir/child
```

## PARAMETERS

### -ClientRequestId

An opaque, globally-unique, client-generated string identifier for the request.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -DirectoryPath

The directory path within the share, e.g. parent/child. The parent must exist.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Metadata

Metadata as key=value pairs.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SasToken

A shared access signature. Alternative to -StorageAccountKey.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ShareName

The share name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -StorageAccountKey

Storage account key.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -StorageAccountName

Storage account name. Used with the share name and directory path when -Url is not given.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Timeout

The timeout parameter is expressed in seconds.

```yaml
Type: System.Int32
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Url

The directory URL. Alternative to -StorageAccountName, -ShareName and -DirectoryPath.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

This cmdlet does not accept pipeline input.

## OUTPUTS

### Microsoft.Azure.AzClips.Extensions.StorageFile.Models.ShareDirectory

The properties of the new directory.

## NOTES

## RELATED LINKS

- [Create Directory REST API](https://learn.microsoft.com/rest/api/storageservices/create-directory)
- [Get-AzStorageDirectory](Get-AzStorageDirectory.md)
- [Remove-AzStorageDirectory](Remove-AzStorageDirectory.md)
- [Get-AzStorageFile](Get-AzStorageFile.md)
