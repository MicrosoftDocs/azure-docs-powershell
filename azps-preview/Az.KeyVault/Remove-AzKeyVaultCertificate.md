---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.KeyVault.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.KeyVault
ms.date: 10/16/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzKeyVaultCertificate
---

# Remove-AzKeyVaultCertificate

## SYNOPSIS

Soft-delete all versions of a certificate after confirmation.

## SYNTAX

### __AllParameterSets

```
Remove-AzKeyVaultCertificate -Name <string> [-PassThru] [-VaultName <string>] [-VaultUrl <string>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

None.


## DESCRIPTION

Deletes all versions and the associated policy from an existing public-cloud vault. Requires certificates/delete. Honors ShouldProcess and high-impact confirmation. PassThru returns service recovery metadata without deleted-state polling; by default no result is emitted. Never purges or changes retention settings. Use Undo-AzKeyVaultCertificateRemoval to recover the certificate within the retention period.

## EXAMPLES

### Example 1

Preview deletion without sending a request.

```powershell
Remove-AzKeyVaultCertificate -VaultName myvault -Name app-tls -WhatIf
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

### -PassThru

Return the deleted public certificate and recovery metadata. By default this cmdlet does not emit a result.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### Microsoft.Azure.Azclips.Extensions.KeyVault.Customization.DeletedCertificateResult

The deleted public certificate and recovery metadata when PassThru is specified.

## NOTES

Public Azure only. Uses an existing vault and profile. Use Undo-AzKeyVaultCertificateRemoval for certificate recovery. Purge, backup/restore and standalone key operations are not included.

## RELATED LINKS


- [Key Vault certificate REST API](https://learn.microsoft.com/rest/api/keyvault/certificates/)
