---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Storage.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Storage
ms.date: 11/12/2026
PlatyPS schema version: 2024-05-01
title: Start-AzStorageFileCopy
---

# Start-AzStorageFileCopy

## SYNOPSIS

Starts an asynchronous copy into a file.

## SYNTAX

### Default (Default)

```
Start-AzStorageFileCopy [-Url <string>] [-StorageAccountName <string>] [-ShareName <string>]
 [-FilePath <string>] [-StorageAccountKey <string>] [-SasToken <string>] [-SourceUrl <string>]
 [-Metadata <string[]>] [-Timeout <int>] [-ClientRequestId <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Starts a server-side copy into a file in a file share. The source must be an Azure file or blob; a source in another account must be readable, for example through a SAS token. The cmdlet returns once the copy is scheduled; check its status with Get-AzStorageFile. Authenticate with -StorageAccountName and -StorageAccountKey, or with -SasToken. Alternatively, pass the full resource URL with -Url.

## EXAMPLES

### Example 1: Copy a file within the share

```powershell
Start-AzStorageFileCopy -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare -FilePath mydir/copy.txt -SourceUrl https://mystorageaccount.file.core.windows.net/myshare/mydir/myfile.txt
```

### Example 2: Copy a blob into a file

```powershell
Start-AzStorageFileCopy -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare -FilePath mydir/fromblob.txt -SourceUrl https://mystorageaccount.blob.core.windows.net/mycontainer/myblob.txt
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

### -FilePath

The destination file path within the share, e.g. dir/file.txt.

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

Destination metadata as key=value pairs. The source metadata is copied when not given.

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

### -SourceUrl

The source file or blob URL. It must be in the destination account or carry a SAS.

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

Storage account name. Used with the share name and file path when -Url is not given.

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

The destination file URL. Alternative to -StorageAccountName, -ShareName and -FilePath.

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

### Microsoft.Azure.AzClips.Extensions.StorageFile.Models.FileCopyResult

The copy ID and copy status of the scheduled copy.

## NOTES

## RELATED LINKS

- [Copy File REST API](https://learn.microsoft.com/rest/api/storageservices/copy-file)
- [Get-AzStorageFile](Get-AzStorageFile.md)
- [Start-AzStorageBlobCopy](Start-AzStorageBlobCopy.md)
