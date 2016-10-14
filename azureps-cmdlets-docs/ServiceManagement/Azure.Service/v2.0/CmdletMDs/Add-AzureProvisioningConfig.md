---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\New-AzureVM.md
schema: 2.0.0
---

# Add-AzureProvisioningConfig

## SYNOPSIS
Adds provisioning configuration for an Azure virtual machine.

## SYNTAX

### Windows (Default)
```
Add-AzureProvisioningConfig -VM <IPersistentVM> [-DisableGuestAgent] [-CustomDataFile <String>] [-Windows]
 [-AdminUsername <String>] [-Password <String>] [-ResetPasswordOnFirstLogon] [-DisableAutomaticUpdates]
 [-NoRDPEndpoint] [-TimeZone <String>] [-Certificates <CertificateSettingList>] [-EnableWinRMHttp]
 [-DisableWinRMHttps] [-WinRMCertificate <X509Certificate2>] [-X509Certificates <X509Certificate2[]>]
 [-NoExportPrivateKey] [-NoWinRMEndpoint] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### Linux
```
Add-AzureProvisioningConfig -VM <IPersistentVM> [-DisableGuestAgent] [-Linux] [-LinuxUser <String>]
 [-DisableSSH] [-NoSSHEndpoint] [-NoSSHPassword] [-SSHPublicKeys <SSHPublicKeyList>]
 [-SSHKeyPairs <SSHKeyPairList>] [-CustomDataFile <String>] [-Password <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### WindowsDomain
```
Add-AzureProvisioningConfig -VM <IPersistentVM> [-DisableGuestAgent] [-CustomDataFile <String>]
 -AdminUsername <String> [-WindowsDomain] [-Password <String>] [-ResetPasswordOnFirstLogon]
 [-DisableAutomaticUpdates] [-NoRDPEndpoint] [-TimeZone <String>] [-Certificates <CertificateSettingList>]
 -JoinDomain <String> -Domain <String> -DomainUserName <String> -DomainPassword <String>
 [-MachineObjectOU <String>] [-EnableWinRMHttp] [-DisableWinRMHttps] [-WinRMCertificate <X509Certificate2>]
 [-X509Certificates <X509Certificate2[]>] [-NoExportPrivateKey] [-NoWinRMEndpoint] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureProvisioningConfig** cmdlet adds provisioning configuration information to an Azure virtual machine configuration.
You can use the configuration object to create a virtual machine.

This cmdlet supports different provisioning configurations, including standalone Windows servers, Windows servers joined to an Active Directory domain, and Linux-based servers.

To create an Active Directory domain joined server, specify the fully qualified domain name of the Active Directory domain and the domain credentials of a user who has permission to join the virtual machine to the domain.

## EXAMPLES

### Example 1: Create a standalone virtual machine
```
PS C:\>New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" | New-AzureVM -ServiceName "ContosoService"
```

This command creates a virtual machine configuration object by using the New-AzureVMConfig cmdlet.
The command passes that object to the current cmdlet by using the pipeline operator.
The current cmdlet adds provisioning configuration for a virtual machine that runs the Windows operating system.
The configuration includes the administrator user name and password.
The command passes the configuration to the New-AzureVM cmdlet, which creates the virtual machine.

### Example 2: Create a domain joined virtual machine
```
PS C:\>New-AzureVMConfig -Name "DomainVM" -InstanceSize Small -ImageName "Image09" | Add-AzureProvisioningConfig -WindowsDomain -Password "password" -AdminUsername "AdminMain" -ResetPasswordOnFirstLogon -JoinDomain "contoso.com" -Domain "contoso" -DomainUserName "DomainAdminUser" -DomainPassword "DomainPassword" -MachineObjectOU 'OU=AzureVMs,DC=contoso,DC=com' | New-AzureVM -ServiceName "ContosoService"
```

This command creates a virtual machine configuration object, and then passes it to the current cmdlet.
The current cmdlet adds provisioning configuration for a virtual machine to be joined with the contoso domain.
The command includes user name and password necessary to join the virtual machine to the domain.
The configuration requires the user to change the user password at the first logon.
The command creates the virtual machine based on the provisioning object.

### Example 3: Create a Linux-based virtual machine
```
PS C:\>New-AzureVMConfig -Name "LinuxVM" -InstanceSize Small -ImageName "LinuxImage03" | Add-AzureProvisioningConfig -Linux -LinuxUser "LinuxRoot" -Password "password" | New-AzureVM -ServiceName "ContosoService"
```

This command creates a virtual machine configuration object, and then passes it to the current cmdlet.
The current cmdlet adds provisioning configuration for a virtual machine that runs the Linux operating system.
The configuration includes the root user name and password.
The command creates the virtual machine based on the provisioning object.

### Example 4: Create a virtual machine that includes certificates for WinRM
```
PS C:\>$certs = Get-ChildItem Cert:\CurrentUser\My
New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image11" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -WinRMCertificate $certs[0] -X509Certificates $certs[1], $certs[2] | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

The first command gets certificates from a certificate store, and then stores them in the $certs array variable.

The second command creates a virtual machine configuration object, and then passes it to the current cmdlet.
The current cmdlet adds provisioning configuration that includes certificates for WinRM.
The command creates the virtual machine based on the provisioning object.

### Example 5: Create a virtual machine that has WinRM enabled over HTTP
```
PS C:\>New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image14" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -EnableWinRMHttp | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

This command creates a virtual machine configuration object, and then passes it to the current cmdlet.
The current cmdlet adds provisioning configuration that has WinRM enabled over HTTP.
The command creates the virtual machine based on the provisioning object.

### Example 6: Create a virtual machine that has WinRM disabled over HTTPS
```
PS C:\>New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -DisableWinRMHttps | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

This command creates a virtual machine configuration object, and then passes it to the current cmdlet.
The current cmdlet adds provisioning configuration that disables WinRM over HTTPS.
The command creates the virtual machine based on the provisioning object.

### Example 7: Create a virtual machine with no key export
```
PS C:\>$certs = Get-ChildItem Cert:\CurrentUser\My
New-AzureVMConfig -Name "NonDomainVM" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -Password "password" -AdminUsername "AdminMain" -X509Certificates $certs[0], $certs[1] -NoExportPrivateKey | New-AzureVM -ServiceName "ContosoService" -WaitForBoot
```

The first command gets certificates from a certificate store, and then stores them in the $certs array variable.

The second command creates a virtual machine configuration object, and then passes it to the current cmdlet.
The current cmdlet adds provisioning configuration for a virtual machine that includes certificates and does not export private keys.
The command creates the virtual machine based on the provisioning object.

## PARAMETERS

### -VM
Specifies a virtual machine object.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DisableGuestAgent
Indicates that this configuration disables the infrastructure as a service (IaaS) guest agent.

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

### -CustomDataFile
Specifies a data file for the virtual machine.
This cmdlet encodes the contents of the file as Base64.
The file must be less than 64 kilobytes long.

If the guest operating system is the Windows operating system, this configuration saves this data as a binary file named %SYSTEMDRIVE%\AzureData\CustomData.bin.

If the guest operating system is Linux, this configuration passes the data by using the ovf-env.xml file.
Configuration copies that file to the /var/lib/waagent directory.
The agent also stores the Base64 encoded data in /var/lib/waagent/CustomData.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Windows
Indicates that this configuration creates a standalone virtual machine that runs the Windows operating system.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AdminUsername
Specifies the user name of the Administrator account that this configuration creates on the virtual machine.

```yaml
Type: String
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password of the administrator account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResetPasswordOnFirstLogon
Indicates that the virtual machine requires the user to change the password at the first logon.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableAutomaticUpdates
Indicates that this configuration disables automatic updates.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoRDPEndpoint
Indicates that this configuration creates a virtual machine without a remote desktop endpoint.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeZone
Specifies the time zone for the virtual machine, for example, Pacific Standard Time or Canada Central Standard Time.

```yaml
Type: String
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificates
Specifies a set of certificates that this configuration installs on the virtual machine.

```yaml
Type: CertificateSettingList
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableWinRMHttp
Indicates that this configuration enables WinRM over HTTP.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableWinRMHttps
Indicates that this configuration disables Windows Remote Management (WinRM) on HTTPS.
By default, WinRM is enabled over HTTPS.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WinRMCertificate
Specifies a certificate that this configuration associates to a WinRM endpoint.

```yaml
Type: X509Certificate2
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -X509Certificates
Specifies an array of X509 certificates that are deployed to a hosted service.

```yaml
Type: X509Certificate2[]
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoExportPrivateKey
Indicates that this configuration does not upload the private key.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWinRMEndpoint
Indicates that this configuration does not add a WinRM endpoint for the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: Windows, WindowsDomain
Aliases: 

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

### -Linux
Indicates that this configuration creates a Linux configuration.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxUser
Specifies the user name of the Linux administrative account that this configuration creates on the virtual machine.

```yaml
Type: String
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableSSH
Indicates that this configuration disables SSH.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoSSHEndpoint
Indicates that this configuration creates a virtual machine without an SSH endpoint.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoSSHPassword
Indicates that this configuration creates a virtual machine without an SSH password.

```yaml
Type: SwitchParameter
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHPublicKeys
Specifies SSH public keys.

```yaml
Type: SSHPublicKeyList
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SSHKeyPairs
Specifies SSH key pairs.

```yaml
Type: SSHKeyPairList
Parameter Sets: Linux
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsDomain
Indicates that this configuration creates Windows server that is joined to an Active Directory domain.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JoinDomain
Specifies the fully qualified domain name (FQDN) of the domain to join.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies the name of the domain of the account that has permission to add the computer to a domain.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainUserName
Specifies the name of the user account that has permission to add the computer to a domain.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainPassword
Specifies the password of the user account that has permission to add the computer to a domain.

```yaml
Type: String
Parameter Sets: WindowsDomain
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineObjectOU
Specifies the fully qualified name of the organizational unit (OU) in which the configuration creates the computer account.

```yaml
Type: String
Parameter Sets: WindowsDomain
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

[New-AzureVM](.\New-AzureVM.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

