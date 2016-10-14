---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\Get-AzureSiteRecoveryVaultSettings.md
schema: 2.0.0
---

# Import-AzureSiteRecoveryVaultSettingsFile

## SYNOPSIS
Imports a vault settings file for Azure Site Recovery.

## SYNTAX

```
Import-AzureSiteRecoveryVaultSettingsFile [-Path] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzureSiteRecoveryVaultSettingsFile** cmdlet imports a vault settings file for Microsoft Azure Site Recovery.
You specify a vault settings file when you connect to an Azure Site Recovery vault.
You can download the vault settings file from an Azure Site Recovery vault when you log on to the Azure portal.

## EXAMPLES

### Example 1: Import a vault settings file
```
PS C:\>Import-AzureSiteRecoveryVaultSettingsFile -Path "C:\Users\Contoso\Contosovault Monday, October 6, 2014.VaultCredentials"
VERBOSE: Vault Settings File path: C:\Users\Contoso\Contosovault Monday, October 6, 2014.VaultCredentials

ResourceName                                                CloudServiceName
------------                                                ----------------
Contosovault                                              RecoveryServices-6JP23WE3SKKOM5AFQG2YQAI22MNOWK52QDKWMUP...
```

This command imports the vault settings file at the specified path.

## PARAMETERS

### -Path
Specifies the full path to the vault settings file to import.
You can download this file from the Azure Site Recovery vault portal and store it locally.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSiteRecoveryVaultSettings](.\Get-AzureSiteRecoveryVaultSettings.md)

