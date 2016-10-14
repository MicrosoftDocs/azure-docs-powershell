---
external help file: Microsoft.Azure.Commands.KeyVault.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=824805
schema: 2.0.0
---

# Restore-AzureKeyVaultKey

## SYNOPSIS
Creates a key in a key vault from a backed-up key.

## SYNTAX

```
Restore-AzureKeyVaultKey [-VaultName] <String> [-InputFile] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Restore-AzureKeyVaultKey** cmdlet creates a key in the specified key vault.
This key is a replica of the backed-up key in the input file and has the same name as the original key.
If the key vault already has a key by the same name, this cmdlet fails instead of overwriting the original key.
If the backup contains multiple versions of a key, all versions are restored.

The key vault that you restore the key into can be different from the key vault that you backed up the key from.
However, the key vault must use the same subscription and be in an azure_2 region in the same geography (for example, North America).
See the Microsoft Azure Trust Centerhttps://azure.microsoft.com/support/trust-center/ (https://azure.microsoft.com/support/trust-center/) for the mapping of azure_2 regions to geographies.

## EXAMPLES

### Example 1: Restore a backed-up key
```
PS C:\>Restore-AzureKeyVaultKey -VaultName 'MyKeyVault' -InputFile "C:\Backup.blob"
```

This command restores a key, including all of its versions, from the backup file named Backup.blob into the key vault named MyKeyVault.

## PARAMETERS

### -InputFile
Specifies the input file that contains the backup of the key to restore.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultName
Specifies the name of the key vault into which to restore the key.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureKeyVaultKey](.\Add-AzureKeyVaultKey.md)

[Backup-AzureKeyVaultKey](.\Backup-AzureKeyVaultKey.md)

[Get-AzureKeyVaultKey](.\Get-AzureKeyVaultKey.md)

[Remove-AzureKeyVaultKey](.\Remove-AzureKeyVaultKey.md)

