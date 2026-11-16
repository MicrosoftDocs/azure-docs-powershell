---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.KeyVault.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.KeyVault
ms.date: 09/18/2026
PlatyPS schema version: 2024-05-01
title: Get-AzKeyVaultSecret
---

# Get-AzKeyVaultSecret

## SYNOPSIS

Get secret metadata, list secrets or versions, or explicitly retrieve a plaintext value.

## SYNTAX

### List (Default)

```
Get-AzKeyVaultSecret [-MaxResults <int>] [-VaultName <string>] [-VaultUrl <string>]
 [-Profile <string>] [<CommonParameters>]
```

### Get

```
Get-AzKeyVaultSecret -Name <string> [-Version <string>] [-AsPlainText] [-VaultName <string>]
 [-VaultUrl <string>] [-Profile <string>] [<CommonParameters>]
```

### Versions

```
Get-AzKeyVaultSecret -Name <string> -IncludeVersions [-MaxResults <int>] [-VaultName <string>]
 [-VaultUrl <string>] [-Profile <string>] [<CommonParameters>]
```

## ALIASES

None.

## DESCRIPTION

Without Name, lists secret metadata across all pages. With Name, gets the latest or specified version. IncludeVersions lists version metadata. Values are omitted unless AsPlainText is supplied. Use either VaultName or VaultUrl for an existing Azure public-cloud vault and a signed-in profile with secrets/get or secrets/list permission.

## EXAMPLES

### Example 1

List metadata, retrieve one secret's metadata, then explicitly retrieve its value when required.

```powershell
Get-AzKeyVaultSecret -VaultName myvault
Get-AzKeyVaultSecret -VaultName myvault -Name app-password
Get-AzKeyVaultSecret -VaultName myvault -Name app-password -IncludeVersions
Get-AzKeyVaultSecret -VaultName myvault -Name app-password -AsPlainText
```

## PARAMETERS

### -AsPlainText

Return the plaintext value directly. Without this switch, output contains metadata only. Plaintext may be captured by the terminal or calling process.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### -IncludeVersions

List versions and their metadata without retrieving secret values.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Versions
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -MaxResults

Page size from 1 to 25. All pages are returned; this is not a total result limit.

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
- Name: Versions
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

Secret name containing letters, digits or hyphens.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Get
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: Versions
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Profile

Named connection profile. Defaults to the active profile.

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

### -VaultName

Azure public-cloud vault name. Specify this or VaultUrl, not both.

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

### -VaultUrl

Root HTTPS URL of the vault, such as https://myvault.vault.azure.net/.

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

### -Version

Version identifier. Omit to retrieve the latest version.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.KeyVault.Customization.SecretMetadata

Secret identifiers and attributes without a secret-value property.

### System.String

The secret value, only when AsPlainText is supplied.

## NOTES

AzureCloud only. URI aliases, wildcard names and private-key export convenience workflows are not included. Use Undo-AzKeyVaultSecretRemoval to recover a soft-deleted secret by name.

## RELATED LINKS

[Set-AzKeyVaultSecret](Set-AzKeyVaultSecret.md)

