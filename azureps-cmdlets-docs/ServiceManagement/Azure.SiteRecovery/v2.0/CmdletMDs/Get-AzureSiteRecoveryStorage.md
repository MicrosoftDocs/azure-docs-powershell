---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\New-AzureSiteRecoveryStorageMapping.md
schema: 2.0.0
---

# Get-AzureSiteRecoveryStorage

## SYNOPSIS
Gets Azure Site Recovery Storages for the current vault.

## SYNTAX

```
Get-AzureSiteRecoveryStorage -Server <ASRServer> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryStorage** cmdlet gets Azure Site Recovery Storages for the current Azure Site Recovery vault.

## EXAMPLES

### Example 1: Get site recovery storage
```
PS C:\>$Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryStorage -Server $Servers[0]
Name           : phase2PrimaryStorageClassification
ID             : 1c1d0c0b-0c50-4675-af1a-1fdac70dbb6d
FabricObjectID : 1c1d0c0b-0c50-4675-af1a-1fdac70dbb6d
ServerId       : 774859b0-1966-48cc-9df7-759c441b7a8c
Type           : Classification
FabricType     : VMM

Name           : phase2RecoveryStorageClassification
ID             : 20cf8d92-fd5d-4872-985a-0f4562b8a0bf
FabricObjectID : 20cf8d92-fd5d-4872-985a-0f4562b8a0bf
ServerId       : 774859b0-1966-48cc-9df7-759c441b7a8c
Type           : Classification
FabricType     : VMM
```

The first command cmdlet gets servers for the current Azure Site Recovery vault by using the **Get-AzureSiteRecoveryServer** cmdlet.
The command stores the Microsoft Azure Site Recovery servers in the $Servers array variable.

The second command gets the site recovery storage for the first server in the $Servers array.

## PARAMETERS

### -Server
Specifies a server for Azure Site Recovery Storage.
To obtain an **ASRServer** object, use the **Get-AzureSiteRecoveryServer** cmdlet.

```yaml
Type: ASRServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[New-AzureSiteRecoveryStorageMapping](.\New-AzureSiteRecoveryStorageMapping.md)

[Get-AzureSiteRecoveryServer](.\Get-AzureSiteRecoveryServer.md)

