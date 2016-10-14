---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\Get-AzureSiteRecoveryVault.md
schema: 2.0.0
---

# New-AzureSiteRecoveryVault

## SYNOPSIS
Creates an Azure Site Recovery vault.

## SYNTAX

```
New-AzureSiteRecoveryVault -Name <String> -Location <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSiteRecoveryVault** cmdlet creates an Azure Site Recovery vault.

## EXAMPLES

### Example 1: Create a vault
```
PS C:\>New-AzureSiteRecoveryVault -Location "West US" -Name "ContosoVault" 
Response
--------
Vault has been created
```

This command creates a vault named ContosoVault in the West US location.

## PARAMETERS

### -Location
Specifies the name of the geo to which the vault belongs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the vault to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-AzureSiteRecoveryVault](.\Get-AzureSiteRecoveryVault.md)

