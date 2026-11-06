---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.KeyVault.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.KeyVault
ms.date: 10/16/2026
PlatyPS schema version: 2024-05-01
title: Export-AzKeyVaultCertificate
---

# Export-AzKeyVaultCertificate

## SYNOPSIS

Download a public X509 certificate as PEM or DER.

## SYNTAX

### __AllParameterSets

```
Export-AzKeyVaultCertificate -Name <string> -FilePath <string> [-Version <string>]
 [-Encoding <string>] [-VaultName <string>] [-VaultUrl <string>] [-Profile <string>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## ALIASES

None.


## DESCRIPTION

Reads and validates the public certificate before writing a new file. Existing destinations are never overwritten. Requires certificates/get. Never follows backing secret/key references or exports private keys. WhatIf prevents both the network read and local file creation.

## EXAMPLES

### Example 1

Download the public certificate in DER format.

```powershell
Export-AzKeyVaultCertificate -VaultName myvault -Name app-tls -FilePath ./app.cer -Encoding DER
```

## PARAMETERS

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- cf
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

### -Encoding

PEM (default) or DER public certificate encoding.

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

New destination file. Existing files or directories are rejected.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

Certificate name containing 1-127 letters, digits or hyphens. Omit only when listing.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- CertificateName
ParameterSets:
- Name: (All)
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

Named connection profile for the selected vault.

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

Existing Azure public-cloud vault name. Use instead of VaultUrl.

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

Root HTTPS URL of an existing Azure public-cloud vault. Use instead of VaultName.

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

Certificate version identifier. Omit for latest. Cannot be combined with a name-wide policy update.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- CertificateVersion
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

### -WhatIf

Runs the command in a mode that only reports what would happen without performing the actions.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- wi
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

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.KeyVault.Customization.CertificateDownloadResult

Reads and validates the public certificate before writing a new file. Existing destinations are never overwritten. Requires certificates/get. Never follows backing secret/key references or exports private keys. WhatIf prevents both the network read and local file creation.

## NOTES

Public Azure only. Uses an existing vault and profile. Use Undo-AzKeyVaultCertificateRemoval for certificate recovery. Purge, backup/restore and standalone key operations are not included.

## RELATED LINKS


- [Key Vault certificate REST API](https://learn.microsoft.com/rest/api/keyvault/certificates/)
