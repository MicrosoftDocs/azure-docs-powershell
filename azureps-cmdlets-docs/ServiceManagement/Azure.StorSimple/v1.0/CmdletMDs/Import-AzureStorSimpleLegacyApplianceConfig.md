---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Import-AzureStorSimpleLegacyVolumeContainer.md
schema: 2.0.0
---

# Import-AzureStorSimpleLegacyApplianceConfig

## SYNOPSIS
Imports a configuration file.

## SYNTAX

```
Import-AzureStorSimpleLegacyApplianceConfig [-ConfigFilePath] <String> [-TargetDeviceName] <String>
 [-ConfigDecryptionKey] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-AzureStorSimpleLegacyApplianceConfig** cmdlet imports the configuration file from the legacy appliance.
That file contains information about volume containers, backup policies, and storage account credentials for the azure_2 StorSimple service.
This cmdlet returns the legacy appliance configuration metadata.

## EXAMPLES

### Example 1: Import a configuration file
```
PS C:\>Import-AzureStorSimpleLegacyApplianceConfig -ConfigFilePath "C:\MigrationData\LegacyStorSimpleConfig.sse" -TargetDeviceName "8100-123456789" -ConfigDecryptionKey "fWs793hHVhR90NKdDYTeNq"
LegacyConfigId      : e2d5c9b1-b528-4c21-b8ae-533feefc8a41
ImportedOn          : 4/8/2015 7:23:04 PM
ConfigFile          : D:\configs\StorSimpleConfig_27_Mar_15_12_19.xml.sse
TargetApplianceName : Arunkm-N4
Details             : Available Cloud Configuration(s) for migration : 
                          Cloud Configuration(s) 1    : TC8Cloud[Stingray19-FP6] 
                          Cloud Configuration(s) 2    : fulle_cc4
                          Cloud Configuration(s) 3    : fulle_cc2
                          Cloud Configuration(s) 4    : fulle_cc3
                          Cloud Configuration(s) 5    : TC9Cloud[Stingray18-FP3] 
                          Cloud Configuration(s) 6    : fulle_cc1
                          Cloud Configuration(s) 7    : Container-New[Stingray19-FP6] 
                          Cloud Configuration(s) 8    : TC6Cloud[Stingray19-FP6] 
                          Cloud Configuration(s) 9    : TC7Cloud[Stingray18-FP3] 

Result              : Successfully imported config from the legacy appliance! 
Save the legacy config id and cloud configuration(s) for future reference.
```

This command imports the configuration file at the specified path.
The command includes the key to decrypt the file.

## PARAMETERS

### -ConfigDecryptionKey
Specifies the decryption key for the configuration of the legacy appliance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigFilePath
Specifies the absolute path of the configuration file to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FilePath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies an azure_2 profile.

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

### -TargetDeviceName
Specifies the name of the target device as presented in the portal.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### LegacyApplianceConfiguration
This cmdlet returns the details of the configuration.
The **LegacyApplianceConfiguration** object contains the following information: configuration ID, volume container names, access control records, backup policies, bandwidth settings, volume containers, storage account credentials, and volumes.

## NOTES

## RELATED LINKS

[Import-AzureStorSimpleLegacyVolumeContainer](.\Import-AzureStorSimpleLegacyVolumeContainer.md)

