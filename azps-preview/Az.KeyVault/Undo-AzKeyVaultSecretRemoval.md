---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.KeyVault.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.KeyVault
ms.date: 10/08/2026
PlatyPS schema version: 2024-05-01
title: Undo-AzKeyVaultSecretRemoval
---

# Undo-AzKeyVaultSecretRemoval

## SYNOPSIS

Recover a soft-deleted secret and its versions.

## SYNTAX

### __AllParameterSets

```
Undo-AzKeyVaultSecretRemoval -Name <string> [-VaultName <string>] [-VaultUrl <string>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

None.

## DESCRIPTION

Recover a secret within the soft-delete retention period in an existing Azure public-cloud vault. Requires secrets/recover permission. Specify either VaultName or the root HTTPS VaultUrl. Returns metadata for the recovered secret without its value. Supports WhatIf and Confirm. A purged secret or a secret whose retention period has expired cannot be recovered.

## EXAMPLES

### Example 1

Recover a deleted secret by name.

```powershell
Undo-AzKeyVaultSecretRemoval -VaultName myvault -Name app-password
```

### Example 2

Preview recovery without sending a request.

```powershell
Undo-AzKeyVaultSecretRemoval -VaultName myvault -Name app-password -WhatIf
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

Name of the soft-deleted secret. Recovery applies to the secret and its versions, not an individual version.

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

### -Profile

Named connection profile. When omitted, uses the active profile.

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

Azure public-cloud vault name. Use either VaultName or VaultUrl.

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

Root HTTPS URL of an Azure public-cloud vault, such as https://myvault.vault.azure.net/. Use instead of VaultName.

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

### Microsoft.Azure.Azclips.Extensions.KeyVault.Customization.SecretMetadata

Recovered-secret metadata, including its identifier, attributes and tags when returned by the service. The result does not contain the secret value.

## NOTES

Returns the recovery response without polling for subsequent read availability. Supports name-based recovery only; legacy Id and InputObject parameter sets are not included. Unlike classic Az.KeyVault, output is metadata-only rather than a SecureString-bearing secret object. Purge, deleted-secret listing and backup restore are not implemented.

## RELATED LINKS

[Key Vault soft-delete overview](https://learn.microsoft.com/azure/key-vault/general/soft-delete-overview)

