---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Storage.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Storage
ms.date: 11/12/2026
PlatyPS schema version: 2024-05-01
title: Get-AzStorageFile
---

# Get-AzStorageFile

## SYNOPSIS

Lists the files and directories in a file share, or gets the properties of a file.

## SYNTAX

### List (Default)

```
Get-AzStorageFile [-Url <string>] [-StorageAccountName <string>] [-ShareName <string>]
 [-DirectoryPath <string>] [-StorageAccountKey <string>] [-SasToken <string>]
 [-Sharesnapshot <string>] [-Prefix <string>] [-Marker <string>] [-Maxresults <int>]
 [-Timeout <int>] [-ClientRequestId <string>] [<CommonParameters>]
```

### Get

```
Get-AzStorageFile [-Url <string>] [-StorageAccountName <string>] [-ShareName <string>]
 [-StorageAccountKey <string>] [-SasToken <string>] [-Timeout <int>] [-ClientRequestId <string>]
 [-FilePath <string>] [-Snapshot <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Without -FilePath, lists the files and directories in -DirectoryPath, or in the share root when no directory is given, and follows continuation markers until all pages are returned. With -FilePath, gets the system properties and metadata of a single file, such as its content length, without downloading its content. Authenticate with -StorageAccountName and -StorageAccountKey, or with -SasToken. Alternatively, pass the full resource URL with -Url.

## EXAMPLES

### Example 1: List the share root

```powershell
Get-AzStorageFile -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare
```

### Example 2: List a directory

```powershell
Get-AzStorageFile -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare -DirectoryPath mydir
```

### Example 3: Get the properties of a file

```powershell
Get-AzStorageFile -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare -FilePath mydir/myfile.txt
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

The directory path to list, e.g. parent/child. Lists the share root when not given.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
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

The file path within the share, e.g. dir/file.txt.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Marker

An opaque string value that identifies the portion of the result set to return with this operation.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Maxresults

Specifies the maximum number of entries, directories and files combined, the service scans per page.

```yaml
Type: System.Int32
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Prefix

Filters the results to return only entries whose name begins with the specified prefix.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
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

### -Sharesnapshot

The share snapshot to list.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: List
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Snapshot

The share snapshot to query.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
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

Storage account name. Used with the share name, and the directory or file path, when -Url is not given.

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

The URL of the share or directory to list, or the file URL to get a single file. Alternative to -StorageAccountName, -ShareName, -DirectoryPath and -FilePath.

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

### Microsoft.Azure.AzClips.Extensions.StorageFile.Models.ListFilesAndDirectoriesSegmentResponse

When listing, one result per page, each with the files and directories it contains.

### Microsoft.Azure.AzClips.Extensions.StorageFile.Models.ShareFile

When -FilePath is given, the properties of the file.

## NOTES

## RELATED LINKS

- [List Directories and Files REST API](https://learn.microsoft.com/rest/api/storageservices/list-directories-and-files)
- [Get File Properties REST API](https://learn.microsoft.com/rest/api/storageservices/get-file-properties)
- [Set-AzStorageFileContent](Set-AzStorageFileContent.md)
- [Get-AzStorageFileContent](Get-AzStorageFileContent.md)
- [Get-AzStorageDirectory](Get-AzStorageDirectory.md)
