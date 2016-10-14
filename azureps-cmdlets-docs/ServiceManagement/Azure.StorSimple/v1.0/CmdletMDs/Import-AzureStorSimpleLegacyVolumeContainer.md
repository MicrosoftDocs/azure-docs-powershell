---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleLegacyVolumeContainerStatus.md
schema: 2.0.0
---

# Import-AzureStorSimpleLegacyVolumeContainer

## SYNOPSIS
Starts the migration of volume containers.

## SYNTAX

### MigrateSpecificContainer
```
Import-AzureStorSimpleLegacyVolumeContainer [-LegacyConfigId] <String> [-LegacyContainerNames] <String[]>
 [-SkipACRs] [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### MigrateAllContainer
```
Import-AzureStorSimpleLegacyVolumeContainer [-LegacyConfigId] <String> [-All] [-SkipACRs] [-Force]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzureStorSimpleLegacyVolumeContainer** cmdlet starts the migration of volume containers from a legacy appliance to the target appliance.

## EXAMPLES

### Example 1: Import a legacy volume container
```
PS C:\>Import-AzureStorSimpleLegacyVolumeContainer -LegacyConfigId "c5a831e1-7888-44f4-adf1-92994be630c3" -LegacyContainerNames "OneSDKAzureCloud"
Import started, Please check status with Get-AzureStorSimpleLegacyVolumeContainerStatus commandlet
```

This command imports a legacy volume container for the named container.
The cmdlet starts the import, and then returns a message.

### Example 2: Import all legacy volume containers
```
PS C:\>Import-AzureStorSimpleLegacyVolumeContainer -LegacyConfigId "c5a831e1-7888-44f4-adf1-92994be630c3" -All
Import started, Please check status with Get-AzureStorSimpleLegacyVolumeContainerStatus commandlet
```

This command imports all legacy volume containers from configuration file imported.
The cmdlet starts the import, and then returns a message.

## PARAMETERS

### -All
Indicates that this cmdlet imports all volume containers in the imported configuration file to the target device.

```yaml
Type: SwitchParameter
Parameter Sets: MigrateAllContainer
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet imports volume container on a different device, even if volume container has been imported on a different device.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LegacyConfigId
Specifies the unique ID of the configuration of the legacy appliance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LegacyContainerNames
Specifies an array of volume container names for which the migration plan applies.

```yaml
Type: String[]
Parameter Sets: MigrateSpecificContainer
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
ps_azureprofile_description

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

### -SkipACRs
Indicates that the import process skips access control records for migration.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This command returns the status of the migration import volume container job if it has been successfully started in the appliance.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleLegacyVolumeContainerStatus](.\Get-AzureStorSimpleLegacyVolumeContainerStatus.md)

[Import-AzureStorSimpleLegacyApplianceConfig](.\Import-AzureStorSimpleLegacyApplianceConfig.md)

