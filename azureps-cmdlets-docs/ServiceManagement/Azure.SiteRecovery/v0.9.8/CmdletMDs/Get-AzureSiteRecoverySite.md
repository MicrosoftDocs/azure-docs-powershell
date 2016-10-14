---
external help file: Microsoft.Azure.Commands.RecoveryServices.dll-Help.xml
online version: .\New-AzureSiteRecoverySite.md
schema: 2.0.0
---

# Get-AzureSiteRecoverySite

## SYNOPSIS
Gets Azure Site Recovery sites in a vault.

## SYNTAX

```
Get-AzureSiteRecoverySite [-Vault <ASRVault>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoverySite** cmdlet gets Azure Site Recovery sites in an Azure Site Recovery vault.

## EXAMPLES

### Example 1: Get recovery sites
```
PS C:\>Get-AzureSiteRecoverySite
Type                                    Name                                    ID
----                                    ----                                    --
HyperVSite                              RecoverySite07                          f16829b4-5b01-4209-a6cf-8e0aff1fe328
```

This command gets the recovery sites for the current vault.

## PARAMETERS

### -Vault
Specifies a vault for which to get sites.
To obtain an **ASRVault** object, use the **Get-AzureSiteRecoveryVault** cmdlet.

```yaml
Type: ASRVault
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an Azure profile.

```yaml
Type: AzureProfile
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

[New-AzureSiteRecoverySite](.\New-AzureSiteRecoverySite.md)

[Get-AzureSiteRecoveryVault](.\Get-AzureSiteRecoveryVault.md)

