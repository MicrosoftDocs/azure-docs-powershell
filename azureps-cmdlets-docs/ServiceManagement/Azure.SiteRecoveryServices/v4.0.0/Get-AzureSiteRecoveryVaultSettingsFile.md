---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: AFAA1BDF-3F6A-437A-ADC2-C5EBD970F57D
online version: 
schema: 2.0.0
---

# Get-AzureSiteRecoveryVaultSettingsFile

## SYNOPSIS
Gets the Site Recovery vault settings file.

## SYNTAX

### ByParam (Default)
```
Get-AzureSiteRecoveryVaultSettingsFile -Name <String> -Location <String> [-SiteName <String>]
 [-SiteId <String>] [-Path <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByObject
```
Get-AzureSiteRecoveryVaultSettingsFile -Vault <ASRVault> [-Site <ASRSite>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryVaultSettingsFile** cmdlet gets the settings file for an Azure Site Recovery vault.

## EXAMPLES

### Example 1: Get the settings file for a vault
```
PS C:\> $Vault = Get-AzureSiteRecoveryVault -Name "ContosoVault"
PS C:\> Get-AzureSiteRecoveryVaultSettingsFile -Vault $Vault
FilePath 
-------- 
C:\Users\ContosoAdmin\ContosoVault_2015-02-02T05-39-23.VaultCredentials
```

The first command gets the active Azure Site Recovery vault named ContosoVault by using the **Get-AzureSiteRecoveryVault** cmdlet.
The command stores that vault in the $Vault variable.

The second command gets the settings file for the vault stored in $Vault.

## PARAMETERS

### -Location
Specifies the geographical location to which the vault belongs.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a vault.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the Site Recovery vault settings file.
To store this file locally, download it from the Site Recovery vault portal after the command has finished running.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

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

### -Site
Specifies a site for which to get a settings file.
To obtain a **Site** object, use the **Get-AzureSiteRecoverySite** cmdlet.

```yaml
Type: ASRSite
Parameter Sets: ByObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteId
Specifies the ID of a site.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SiteName
Specifies the name of a site.

```yaml
Type: String
Parameter Sets: ByParam
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vault
Specifies the vault for the site.

```yaml
Type: ASRVault
Parameter Sets: ByObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSiteRecoverySite](./Get-AzureSiteRecoverySite.md)

[Get-AzureSiteRecoveryVault](./Get-AzureSiteRecoveryVault.md)

[Get-AzureSiteRecoveryVaultSettings](./Get-AzureSiteRecoveryVaultSettings.md)

[Import-AzureSiteRecoveryVaultSettingsFile](./Import-AzureSiteRecoveryVaultSettingsFile.md)


