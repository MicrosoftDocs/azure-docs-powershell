---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 649D0A6C-77CE-4E49-AFF8-DF70ABE9FA13
online version: 
schema: 2.0.0
---

# Set-AzureVMDscExtension

## SYNOPSIS
Configures the DSC extension on a virtual machine.

## SYNTAX

```
Set-AzureVMDscExtension [-ReferenceName <String>] [-ConfigurationArgument <Hashtable>]
 [-ConfigurationDataPath <String>] [-ConfigurationArchive] <String> [-ConfigurationName <String>]
 [-ContainerName <String>] [-Force] [-StorageContext <AzureStorageContext>] [-Version <String>]
 [-StorageEndpointSuffix <String>] [-WmfVersion <String>] [-DataCollection <String>] -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureVMDscExtension** cmdlet configures the Desired State Configuration (DSC) extension on a virtual machine.

## EXAMPLES

### Example 1: Configure the DSC extension on a virtual machine
```
PS C:\> Set-AzureVMDscExtension -VM $VM -ConfigurationArchive MyConfiguration.ps1.zip  -ConfigurationName MyConfiguration -ConfigurationArgument @{ Path = 'C:\MyDirectory' }
DeploymentName              : my-vm-svc
Name                        : my-vm
Label                       : 
VM                          : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVM
InstanceStatus              : ReadyRole
IpAddress                   : 10.10.10.10
InstanceStateDetails        : 
PowerState                  : Started
InstanceErrorCode           : 
InstanceFaultDomain         : 0
InstanceName                : my-vm
InstanceUpgradeDomain       : 0
InstanceSize                : Small
AvailabilitySetName         : 
DNSName                     : http://my-vm-svc.cloudapp.net/
Status                      : ReadyRole
GuestAgentStatus            : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVMModel.GuestAgentStatus
ResourceExtensionStatusList : {Contoso.Compute.BGInfo}
PublicIPAddress             : 
PublicIPName                : 
ServiceName                 : my-vm-svc
OperationDescription        : Get-AzureVM
OperationId                 : a0217a7af900c1f8a212299a3333cdbd6
OperationStatus             : OK
```

This command configures the DSC extension on a virtual machine.

The MyConfiguration.ps1.zip package must have been previously uploaded to Azure storage using the **Publish-AzureVMDscConfiguration** command and includes the MyConfiguration.ps1 script and the modules it depends on.

The MyConfiguration argument indicates the specific DSC configuration within the script to execute.
The -*ConfigurationArgument* parameter specifies a hashtable with the arguments that is passed to the configuration function.

### Example 2: Configure the DSC extension on a virtual machine using a path to the configuration data
```
PS C:\> $VM | Set-AzureVMDscExtension -ConfigurationArchive MyConfiguration.ps1.zip  -ConfigurationName MyConfiguration -ConfigurationArgument @{ Credential = Get-Credential } -ConfigurationDataPath MyConfigurationData.psd1 
DeploymentName              : my-vm-svc
Name                        : my-vm
Label                       : 
VM                          : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVM
InstanceStatus              : ReadyRole
IpAddress                   : 10.10.10.10
InstanceStateDetails        : 
PowerState                  : Started
InstanceErrorCode           : 
InstanceFaultDomain         : 0
InstanceName                : my-vm
InstanceUpgradeDomain       : 0
InstanceSize                : Small
AvailabilitySetName         : 
DNSName                     : http://my-vm-svc.cloudapp.net/
Status                      : ReadyRole
GuestAgentStatus            : Microsoft.WindowsAzure.Commands.ServiceManagement.Model.PersistentVMModel.GuestAgentStatus
ResourceExtensionStatusList : {Microsoft.Compute.BGInfo, Microsoft.Powershell.DSC}
PublicIPAddress             : 
PublicIPName                : 
ServiceName                 : my-vm-svc
OperationDescription        : Get-AzureVM
OperationId                 : a0217a7af900c1f8a212299a3333cdbd7
OperationStatus             : OK
```

This command configures the DSC extension on a virtual machine using a path to the configuration data.

## PARAMETERS

### -ConfigurationArchive
Specifies the name of the configuration package (.zip file) that was previously uploaded by Publish-AzureVMDscConfiguration.
This parameter must specify only the name of the file, without any path.

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

### -ConfigurationArgument
Specifies a hashtable specifying the arguments to the configuration function.
The keys correspond to the parameter names and the values to the parameter values.

The acceptable values for this parameter are:

- primitive types
- string
- array
- PSCredential

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationDataPath
Specifies the path of a .psd1 file that specifies the data for the configuration function.
This file must contain a hashtable as described in Separating Configuration and Environment Datahttps://msdn.microsoft.com/en-us/PowerShell/DSC/configData.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName
Specifies the name of the configuration script or module that is invoked by the DSC extension.

The value of this parameter must be the name of one of the configuration functions contained in the scripts or modules packaged in *ConfigurationArchive*.

This cmdlet defaults to the name of the file given by the *ConfigurationArchive* parameter if you omit this parameter, excluding any extension.
For instance, if *ConfigurationArchive* is "SalesWebSite.ps1.zip", the default value for *ConfigurationName* is "SalesWebSite".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerName
Specifies the name of the Azure storage container where the *ConfigurationArchive* is located.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DataCollection
```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet overwrites existing blobs.

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

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
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
Specifies an information variable.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -ReferenceName
Specifies a user-defined string that can be used to refer to an extension.
This parameter is specified when the extension is added to the virtual machine for the first time.
For subsequent updates, you should specify the previously used reference name while you update the extension.
The *ReferenceName* assigned to an extension is returned using the **Get-AzureVM** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageContext
Specifies the Azure storage context that provides the security settings used to access the configuration script.
This context provides read access to the container specified by the *ContainerName* parameter.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEndpointSuffix
Specifies the DNS endpoint suffix for all storage services, for instance, "core.contoso.net".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the specific version of the DSC extension to use.
The default value is set to "1.*" if this parameter is not specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the persistent virtual machine object.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WmfVersion
Specifies the version of the Windows Management Framework (WMF) to install on the virtual machine.
The DSC Extension depends on DSC features that are only available in the WMF updates.
This parameter specifies which version of the update to install on the virtual machine.
The acceptable values for this parameter are:

- 4.0.
Installs KB3000850https://support.microsoft.com/kb/3000850 (https://support.microsoft.com/kb/3000850) on Windows 8.1 or Windows Server 2012 R2, or WMF 4.0https://www.microsoft.com/en-us/download/details.aspx?id=40855 (https://www.microsoft.com/en-us/download/details.aspx?id=40855) on other versions of the Windows operating system, unless a newer version is already installed. 
- 5.0.
Installs the latest release of WMF 5.0https://www.microsoft.com/en-us/download/details.aspx?id=50395 (https://www.microsoft.com/en-us/download/details.aspx?id=50395). 
- latest.
Installs the latest WMF, currently WMF 5.0. 

The default value is latest.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureVMDscExtension](./Get-AzureVMDscExtension.md)

[Remove-AzureVMDscExtension](./Remove-AzureVMDscExtension.md)

[Remove-AzureVMDscExtension](./Remove-AzureVMDscExtension.md)

[Get-AzureVM](./Get-AzureVM.md)

[Publish-AzureVMDscConfiguration](./Publish-AzureVMDscConfiguration.md)


