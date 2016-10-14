---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\Get-AzureSiteRecoveryStorageMapping.md
schema: 2.0.0
---

# New-AzureSiteRecoveryStorageMapping

## SYNOPSIS
Creates a mapping between an Azure Storage object and recovery Storage object.

## SYNTAX

```
New-AzureSiteRecoveryStorageMapping -PrimaryStorage <ASRStorage> -RecoveryStorage <ASRStorage>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureSiteRecoveryStorageMapping** cmdlet creates a mapping between an Azure Site Recovery managed primary Azure Storage object and a recovery Storage object.

## EXAMPLES

### Example 1: Create a mapping between a storage object and a recovery storage object
```
PS C:\>$Servers = Get-AzureSiteRecoveryServer
PS C:\> $Storages = Get-AzureSiteRecoveryStorage -Server $Servers[0]
PS C:\> New-AzureSiteRecoveryStorageMapping -PrimaryStorage $Storages[0] -RecoveryStorage $Storages[1]
```

The first command cmdlet gets servers for the current Azure Site Recovery vault by using the **Get-AzureSiteRecoveryServer** cmdlet.
The command stores the Microsoft Azure Site Recovery servers in the $Servers array variable.

The second command gets the site recovery storage for the first server in the $Servers array, and then stores it in the $Storages.

The final command creates a mapping between the primary network and the recovery network.
The command specifies the primary Storage object as the first element of $Storages.
The command specifies the recovery Storage object as the second element of $Storages.

## PARAMETERS

### -PrimaryStorage
Specifies the primary Storage to map to the recovery Storage.
To obtain an **ASRStorage** object, use the **Get-AzureSiteRecoveryStorage** cmdlet.

```yaml
Type: ASRStorage
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryStorage
Specifies the recovery Storage object.
This cmdlet maps the primary Storage object to the Storage object that this parameter specifies.
To obtain an **ASRStorage** object, use **Get-AzureSiteRecoveryStorage**.

```yaml
Type: ASRStorage
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

[Get-AzureSiteRecoveryStorageMapping](.\Get-AzureSiteRecoveryStorageMapping.md)

[Remove-AzureSiteRecoveryStorageMapping](.\Remove-AzureSiteRecoveryStorageMapping.md)

[Get-AzureSiteRecoveryStorage](.\Get-AzureSiteRecoveryStorage.md)

[Get-AzureSiteRecoveryServer](.\Get-AzureSiteRecoveryServer.md)

