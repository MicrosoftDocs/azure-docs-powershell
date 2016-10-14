---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
online version: .\Get-AzureRmSiteRecoveryRecoveryPlan.md
schema: 2.0.0
---

# New-AzureRmSiteRecoveryRecoveryPlan

## SYNOPSIS
Creates a site recovery plan in Site Recovery.

## SYNTAX

### EnterpriseToEnterprise (Default)
```
New-AzureRmSiteRecoveryRecoveryPlan -Name <String> -PrimaryServer <ASRServer> -RecoveryServer <ASRServer>
 -ProtectionEntityList <ASRProtectionEntity[]> [<CommonParameters>]
```

### EnterpriseToAzure
```
New-AzureRmSiteRecoveryRecoveryPlan -Name <String> -PrimaryServer <ASRServer> [-Azure]
 -FailoverDeploymentModel <String> -ProtectionEntityList <ASRProtectionEntity[]> [<CommonParameters>]
```

### HyperVSiteToAzure
```
New-AzureRmSiteRecoveryRecoveryPlan -Name <String> -PrimarySite <ASRSite> [-Azure]
 -FailoverDeploymentModel <String> -ProtectionEntityList <ASRProtectionEntity[]> [<CommonParameters>]
```

### ByRPFile
```
New-AzureRmSiteRecoveryRecoveryPlan -Path <String> [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmSiteRecoveryRecoveryPlan** cmdlet creates a recovery plan in azure_2 Site Recovery.

A recovery plan gathers virtual machines in a group for the purposes of failover and recovery.

## EXAMPLES

### Example 1: Add a recovery plan to a Site Recovery vault
```
PS C:\>New-AzureRmSiteRecoveryRecoveryPlan -Path "C:\Users\Contoso\Desktop\RecoveryPlan.xml"
```

This command adds the recovery plan named RecoveryPlan.xml to the azure_2 Site Recovery vault.

## PARAMETERS

### -Azure
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FailoverDeploymentModel
@{Text=}

```yaml
Type: String
Parameter Sets: EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
@{Text=}

```yaml
Type: String
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path of the recovery plan file.

```yaml
Type: String
Parameter Sets: ByRPFile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryServer
@{Text=}

```yaml
Type: ASRServer
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimarySite
@{Text=}

```yaml
Type: ASRSite
Parameter Sets: HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionEntityList
@{Text=}

```yaml
Type: ASRProtectionEntity[]
Parameter Sets: EnterpriseToEnterprise, EnterpriseToAzure, HyperVSiteToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryServer
@{Text=}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmSiteRecoveryRecoveryPlan](.\Get-AzureRmSiteRecoveryRecoveryPlan.md)

[Remove-AzureRmSiteRecoveryRecoveryPlan](.\Remove-AzureRmSiteRecoveryRecoveryPlan.md)

[Update-AzureRmSiteRecoveryRecoveryPlan](.\Update-AzureRmSiteRecoveryRecoveryPlan.md)

