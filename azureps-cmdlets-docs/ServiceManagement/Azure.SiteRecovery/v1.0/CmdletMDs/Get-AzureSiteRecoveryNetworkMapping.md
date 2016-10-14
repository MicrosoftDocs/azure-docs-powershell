---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
online version: .\New-AzureSiteRecoveryNetworkMapping.md
schema: 2.0.0
---

# Get-AzureSiteRecoveryNetworkMapping

## SYNOPSIS
Gets mappings of Azure Site Recovery networks for the current vault.

## SYNTAX

### EnterpriseToEnterprise
```
Get-AzureSiteRecoveryNetworkMapping -PrimaryServer <ASRServer> -RecoveryServer <ASRServer>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### EnterpriseToAzure
```
Get-AzureSiteRecoveryNetworkMapping -PrimaryServer <ASRServer> [-Azure] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureSiteRecoveryNetworkMapping** cmdlet gets mappings of Azure Site Recovery networks for the current Azure Site Recovery vault.

## EXAMPLES

### Example 1: Get the mapping between a network and a recovery network
```
PS C:\>$Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -RecoveryServer $Servers[0]
PrimaryServerId     : 774859b0-1966-48cc-9df7-759c441b7a8c
PrimaryNetworkId    : 7cfd636e-5cc2-4e01-873b-8a7aa4962341
PrimaryNetworkName  : phase2RecoveryVMNetwork
RecoveryServerId    : 774859b0-1966-48cc-9df7-759c441b7a8c
RecoveryNetworkId   : d903e2c6-3141-4cef-bfe1-04616cd43cbb
RecoveryNetworkName : phase2PrimaryVMNetwork
PairingStatus       : OK
```

The first command cmdlet gets servers for the current Azure Site Recovery vault by using the **Get-AzureSiteRecoveryServer** cmdlet.
The command stores the Microsoft Azure Site Recovery servers in the $Servers array variable.

The second command gets the mapping between the primary network and the recovery network.
The command specifies the primary server for the network mapping as the first element of $Servers.
The command specifies the server for the recovery network as the second element of $Servers.

### Example 2: Get the mapping between a network and an Azure virtual machine network
```
PS C:\>$Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -Azure
PrimaryServerId     : 774859b0-1966-48cc-9df7-759c441b7a8c
PrimaryNetworkId    : 7cfd636e-5cc2-4e01-873b-8a7aa4962341
PrimaryNetworkName  : phase2RecoveryVMNetwork
RecoveryServerId    : 21a9403c-6ec1-44f2-b744-b4e50b792387
RecoveryNetworkId   : ecb3a462-664f-4f57-873e-d09b5925e1a1
RecoveryNetworkName : AzureVMNetwork
PairingStatus       : OK
```

The first command cmdlet gets servers for the current Azure Site Recovery vault.
The command stores the servers in the $Servers array variable.

The second command gets a mapping between the primary network and an Azure virtual machine network.
The command specifies the primary server for the network as the first element of $Servers.
The command specifies the *Azure* parameter, and, therefore, the command gets the mapping to an Azure virtual machine network.

## PARAMETERS

### -PrimaryServer
Specifies the primary server for the Azure Site Recovery network mapping.
To obtain an **ASRServer** object, use the **Get-AzureSiteRecoveryServer** cmdlet.

```yaml
Type: ASRServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryServer
Specifies the recovery server.
To obtain an **ASRServer**, use **Get-AzureSiteRecoveryServer**.

```yaml
Type: ASRServer
Parameter Sets: EnterpriseToEnterprise
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Azure
Indicates that this cmdlet gets mappings to Azure virtual machine networks.

```yaml
Type: SwitchParameter
Parameter Sets: EnterpriseToAzure
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

[New-AzureSiteRecoveryNetworkMapping](.\New-AzureSiteRecoveryNetworkMapping.md)

[Remove-AzureSiteRecoveryNetworkMapping](.\Remove-AzureSiteRecoveryNetworkMapping.md)

[Get-AzureSiteRecoveryServer](.\Get-AzureSiteRecoveryServer.md)

