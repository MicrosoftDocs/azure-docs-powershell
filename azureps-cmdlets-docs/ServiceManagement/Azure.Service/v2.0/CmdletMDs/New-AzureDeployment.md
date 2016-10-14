---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureDeployment.md
schema: 2.0.0
---

# New-AzureDeployment

## SYNOPSIS
Creates a deployment from a service.

## SYNTAX

```
New-AzureDeployment [-ServiceName] <String> [-Package] <String> [-Configuration] <String> [-Slot] <String>
 [[-Label] <String>] [[-Name] <String>] [-DoNotStart] [-TreatWarningsAsError]
 [-ExtensionConfiguration <ExtensionConfigurationInput[]>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureDeployment** cmdlet creates an Azure deployment from a service that comprises web roles and worker roles.
This cmdlet creates a deployment based on a package file (.cspkg) and a service configuration file (.cscfg).
Specify a name that is unique within deployment environment.

Use the New-AzureVM cmdlet to create a deployment based on Azure virtual machines.

## EXAMPLES

### Example 1: Create a deployment
```
PS C:\>New-AzureDeployment -ServiceName "ContosoService" -Slot "Production" -Package "https://contosostorage.blob.core.windows.net/container06/ContosoPackage.cspkg" -Configuration "C:\packages\ContosoConfiguration.cscfg" -Label "ContosoDeployment"
```

This command creates a production deployment based on a package named ContosoPackage.cspkg and a configuration named ContosoConfiguration.cscfg.
The command specifies a label for the deployment.
It does not specify a name.
This cmdlet creates a GUID as the name.

### Example 2: Create a deployment based on an extension configuration
```
PS C:\>New-AzureDeployment -ServiceName "ContosoService" -Slot "Production" -Package "https://contosostorage.blob.core.windows.net/container06/ContosoPackage.cspkg" -Configuration "C:\packages\ContosoConfiguration.cscfg" -ExtensionConfiguration "C:\packages\ContosoExtensionConfig.cscfg"
```

This command creates a production deployment based on a package and configuration.
The command specifies an extension configuration named ContosoExtensionConfig.cscfg.
This cmdlet creates GUIDs as the name and the label.

## PARAMETERS

### -ServiceName
Specifies the name of the Azure service for the deployment.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Package
Specifies the path or URI of a .cspkg file in storage within the same subscription or project.

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

### -Configuration
Specifies the full path of a service configuration file.

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

### -Slot
Specifies the environment where this cmdlet creates the deployment.
Valid values are: Staging and Production.
The default value is Production.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies a label name for the deployment.
If you do not specify a label, this cmdlet uses a GUID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a deployment name.
If you do not specify a name, this cmdlet uses a GUID.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DeploymentName

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DoNotStart
Specifies that this cmdlet does not start the deployment.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TreatWarningsAsError
Specifies that warning messages are errors.
If you specify this parameter, a warning message causes the deployment to fail.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionConfiguration
Specifies an array of extension configuration objects.

```yaml
Type: ExtensionConfigurationInput[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

[Get-AzureDeployment](.\Get-AzureDeployment.md)

[Get-AzureDeploymentEvent](.\Get-AzureDeploymentEvent.md)

[Move-AzureDeployment](.\Move-AzureDeployment.md)

[New-AzureVM](.\New-AzureVM.md)

[Remove-AzureDeployment](.\Remove-AzureDeployment.md)

[Set-AzureDeployment](.\Set-AzureDeployment.md)

