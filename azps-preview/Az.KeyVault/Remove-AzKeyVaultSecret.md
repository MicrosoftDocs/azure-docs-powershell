---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.KeyVault.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.KeyVault
ms.date: 09/18/2026
PlatyPS schema version: 2024-05-01
title: Remove-AzKeyVaultSecret
---

# Remove-AzKeyVaultSecret

## SYNOPSIS

Delete all versions of a secret without purging it.

## SYNTAX

### __AllParameterSets

```
Remove-AzKeyVaultSecret -Name <string> [-VaultName <string>] [-VaultUrl <string>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

None.

## DESCRIPTION

Delete the secret and all versions in an existing Azure public-cloud vault. Requires secrets/delete permission. Uses PowerShell confirmation and supports WhatIf. Never purges or bypasses purge protection. Returns recovery metadata where provided by the service, without the secret value.

## EXAMPLES

### Example 1

Preview the deletion, then delete with the normal confirmation prompt.

```powershell
Remove-AzKeyVaultSecret -VaultName myvault -Name app-password -WhatIf
Remove-AzKeyVaultSecret -VaultName myvault -Name app-password
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

Secret name. Deletion affects all versions, not a selected version.

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

Deleted-secret metadata, including recovery ID and retention dates when returned by the service.

## NOTES

Use Undo-AzKeyVaultSecretRemoval within the vault's retention period to recover a soft-deleted secret and its versions. A soft-deleted name remains reserved until recovered or removed by the service's retention policy. Purged secrets cannot be recovered.

Purge is a known gap in this preview. Neither a CLI secret purge command nor a PowerShell secret purge parameter is exposed.

## RELATED LINKS

[Get-AzKeyVaultSecret](Get-AzKeyVaultSecret.md)

