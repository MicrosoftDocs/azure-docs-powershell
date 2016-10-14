---
external help file: Microsoft.Azure.Commands.RecoveryServices.Backup.dll-Help.xml
online version: .\Unregister-AzureRmRecoveryServicesBackupManagementServer.md
schema: 2.0.0
---

# Get-AzureRmRecoveryServicesBackupManagementServer

## SYNOPSIS
Gets SCDPM and Azure Backup management servers.

## SYNTAX

```
Get-AzureRmRecoveryServicesBackupManagementServer [[-Name] <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmRecoveryServicesBackupManagementServer** cmdlet gets a list of Backup management servers that are registered in a vault.

There are two types of Backup management servers: System Center Data Protection Manager (SCDPM) and azure_2 Backup management servers.
Backup management servers are installed separately to manage Backup orchestration.

Set the vault context by using the Set-AzureRmRecoveryServicesVaultContext cmdlet before you use the current cmdlet.

## EXAMPLES

### Example 1: Get all Backup management servers
```
PS C:\>Get-AzureRmRecoveryServicesBackupManagementServer
```

This command gets all Backup management servers registered with the vault.

## PARAMETERS

### -Name
Specifies the name of the Backup management server to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

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

[Unregister-AzureRmRecoveryServicesBackupManagementServer](.\Unregister-AzureRmRecoveryServicesBackupManagementServer.md)

