---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.KeyVault.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.KeyVault
ms.date: 10/16/2026
PlatyPS schema version: 2024-05-01
title: Import-AzKeyVaultCertificate
---

# Import-AzKeyVaultCertificate

## SYNOPSIS

Import a PFX or PEM certificate containing a private key.

## SYNTAX

### __AllParameterSets

```
Import-AzKeyVaultCertificate -FilePath <string> -Name <string> [-Password <securestring>]
 [-Enabled <bool>] [-Expires <DateTimeOffset>] [-NotBefore <DateTimeOffset>] [-Tag <hashtable>]
 [-Policy <Object>] [-PolicyPath <string>] [-VaultName <string>] [-VaultUrl <string>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

None.


## DESCRIPTION

Imports a PFX/PKCS#12 or PEM file limited to 1 MiB. PEM requires a PKCS#8 private key. Password is a SecureString. Optional REST-policy content type must match the file. Requires certificates/import. Returns public certificate information, never the private key or password. Public-only imports, certificate collections and pending-CSR merge are not supported.

## EXAMPLES

### Example 1

Read a password securely and import an encrypted PFX.

```powershell
$Host.UI.Write('PFX password: ')
$password = $Host.UI.ReadLineAsSecureString()
Import-AzKeyVaultCertificate -VaultName myvault -Name app-tls -FilePath ./app.pfx -Password $password
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

### -Enabled

Set enabled state explicitly. Omitted values are unchanged for updates.

```yaml
Type: System.Boolean
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

### -Expires

Expiration timestamp, supported through January 2038.

```yaml
Type: System.DateTimeOffset
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

PFX or PEM file containing a private key, limited to 1 MiB. Protect and remove input files according to local policy.

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

### -NotBefore

Not-before timestamp, supported through January 2038.

```yaml
Type: System.DateTimeOffset
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

### -Password

Certificate password as SecureString. Never returned in output.

```yaml
Type: System.Security.SecureString
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

### -Policy

A policy object or JSON using classic CLI or REST field names. CertificatePolicy and PolicyObject are aliases. Use this or PolicyPath, not both.

```yaml
Type: System.Object
DefaultValue: ''
SupportsWildcards: false
Aliases:
- CertificatePolicy
- PolicyObject
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

### -PolicyPath

UTF-8 REST-policy JSON file, limited to 1 MiB. Use instead of Policy.

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

### -Tag

Certificate tags as a hashtable. An empty hashtable clears tags during update.

```yaml
Type: System.Collections.Hashtable
DefaultValue: ''
SupportsWildcards: false
Aliases:
- Tags
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

### Microsoft.Azure.Azclips.Extensions.KeyVault.Customization.CertificateResult

Public certificate information with Name, VaultName, Version, Thumbprint, Certificate, Policy and date properties. Private keys and passwords are not returned.

## NOTES

Public Azure only. Uses an existing vault and profile. Use Undo-AzKeyVaultCertificateRemoval for certificate recovery. Purge, backup/restore and standalone key operations are not included.

## RELATED LINKS


- [Key Vault certificate REST API](https://learn.microsoft.com/rest/api/keyvault/certificates/)
