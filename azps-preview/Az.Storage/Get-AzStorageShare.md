---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Storage.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Storage
ms.date: 11/12/2026
PlatyPS schema version: 2024-05-01
title: Get-AzStorageShare
---

# Get-AzStorageShare

## SYNOPSIS

Lists the file shares in a storage account, or gets the properties of a share.

## SYNTAX

### List (Default)

```
Get-AzStorageShare [-Url <string>] [-StorageAccountName <string>] [-StorageAccountKey <string>]
 [-SasToken <string>] [-Timeout <int>] [-ClientRequestId <string>] [-Prefix <string>]
 [-Marker <string>] [-Maxresults <int>] [<CommonParameters>]
```

### Get

```
Get-AzStorageShare [-Url <string>] [-StorageAccountName <string>] [-ShareName <string>]
 [-StorageAccountKey <string>] [-SasToken <string>] [-Snapshot <string>] [-LeaseId <string>]
 [-Timeout <int>] [-ClientRequestId <string>] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Without -ShareName, lists the file shares in a storage account and follows continuation markers until all pages are returned. Use -Prefix to filter by name. With -ShareName, gets the properties and metadata of a single share, such as its quota and access tier. Authenticate with -StorageAccountName and -StorageAccountKey, or with -SasToken. Alternatively, pass the full resource URL with -Url.

## EXAMPLES

### Example 1: List the file shares

```powershell
Get-AzStorageShare -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY
```

### Example 2: List the file shares whose names start with a prefix

```powershell
Get-AzStorageShare -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -Prefix logs
```

### Example 3: Get the properties of a file share

```powershell
Get-AzStorageShare -StorageAccountName mystorageaccount -StorageAccountKey $env:AZURE_STORAGE_KEY -ShareName myshare
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

### -LeaseId

If specified, the operation only succeeds if the share's lease is active and matches this ID.

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

Specifies the maximum number of shares to return.

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

Filters the results to return only shares whose name begins with the specified prefix.

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

Storage account name. Used with the share name when -Url is not given.

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

The share URL to get a single share, or the file service URL to list shares. Alternative to -StorageAccountName and -ShareName.

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

### Microsoft.Azure.AzClips.Extensions.StorageFile.Models.ShareItemInternal

The file shares in the account, or the properties of the specified share.

## NOTES

## RELATED LINKS

- [List Shares REST API](https://learn.microsoft.com/rest/api/storageservices/list-shares)
- [Get Share Properties REST API](https://learn.microsoft.com/rest/api/storageservices/get-share-properties)
- [New-AzStorageShare](New-AzStorageShare.md)
- [Update-AzStorageShare](Update-AzStorageShare.md)
- [Remove-AzStorageShare](Remove-AzStorageShare.md)
