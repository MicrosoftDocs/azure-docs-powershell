---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 615D2C5D-AB31-45DB-9535-9B9C8E957322
online version: 
schema: 2.0.0
Module Name: Azure
---

# Get-AzureSiteRecoveryNetwork

## SYNOPSIS
Gets information about the networks managed by Site Recovery for the current vault.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSiteRecoveryNetwork -Server <ASRServer> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryNetwork** cmdlet gets information about Azure Site Recovery networks for the current Site Recovery vault.

## EXAMPLES

### Example 1: Get site recovery networks
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryNetwork -Server $Servers[0]
Name                : phase2RecoveryVMNetwork
ID                  : 00001111-aaaa-2222-bbbb-3333cccc4444
FabricObjectID      : 00001111-aaaa-2222-bbbb-3333cccc4444
ServerId            : 774859b0-1966-48cc-9df7-759c441b7a8c
Type                : NoIsolation
FabricType          : VMM
VmNetworkSubnetList : {}

Name                : phase2PrimaryVMNetwork
ID                  : 00001111-aaaa-2222-bbbb-3333cccc4444
FabricObjectID      : 00001111-aaaa-2222-bbbb-3333cccc4444
ServerId            : 774859b0-1966-48cc-9df7-759c441b7a8c
Type                : NoIsolation
FabricType          : VMM
VmNetworkSubnetList : {}
```

The first command cmdlet gets servers for the current Azure Site Recovery vault by using the **Get-AzureSiteRecoveryServer** cmdlet.
The command stores the Site Recovery servers in the $Servers array variable.

The second command gets the site recovery network for the first server in the $Servers array.

## PARAMETERS

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

### -Server
Specifies a Site Recovery server.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS




