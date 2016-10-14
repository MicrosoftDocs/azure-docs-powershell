---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureLocation.md
schema: 2.0.0
---

# New-AzureQuickVM

## SYNOPSIS
Configures and creates an Azure virtual machine.

## SYNTAX

### Windows (Default)
```
New-AzureQuickVM [-Windows] -ServiceName <String> [-Name <String>] -ImageName <String> [-Password <String>]
 [-ReverseDnsFqdn <String>] [-Location <String>] [-AffinityGroup <String>] [-AdminUsername <String>]
 [-Certificates <CertificateSettingList>] [-WaitForBoot] [-DisableWinRMHttps] [-EnableWinRMHttp]
 [-WinRMCertificate <X509Certificate2>] [-X509Certificates <X509Certificate2[]>] [-NoExportPrivateKey]
 [-NoWinRMEndpoint] [-VNetName <String>] [-SubnetNames <String[]>] [-DnsSettings <DnsServer[]>]
 [-HostCaching <String>] [-AvailabilitySetName <String>] [-InstanceSize <String>] [-MediaLocation <String>]
 [-DisableGuestAgent] [-CustomDataFile <String>] [-ReservedIPName <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

### Linux
```
New-AzureQuickVM [-Linux] -ServiceName <String> [-Name <String>] -ImageName <String> [-Password <String>]
 [-ReverseDnsFqdn <String>] [-Location <String>] [-AffinityGroup <String>] [-LinuxUser <String>] [-WaitForBoot]
 [-SSHPublicKeys <SSHPublicKeyList>] [-SSHKeyPairs <SSHKeyPairList>] [-VNetName <String>]
 [-SubnetNames <String[]>] [-DnsSettings <DnsServer[]>] [-HostCaching <String>] [-AvailabilitySetName <String>]
 [-InstanceSize <String>] [-MediaLocation <String>] [-DisableGuestAgent] [-CustomDataFile <String>]
 [-ReservedIPName <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureQuickVM** cmdlet configures and creates an Azure virtual machine.
This cmdlet can deploy a virtual machine into an existing Azure service.
This cmdlet can alternatively create an Azure service that hosts the new virtual machine.

## EXAMPLES

### Example 1: Create a virtual machine
```
PS C:\>New-AzureQuickVM -Windows -ServiceName "ContosoService17" -Name "VirutalMachine01" -ImageName "Image07" -Password "password" -AdminUsername "AdminMain" -WaitForBoot
```

This command creates a virtual machine that runs the Windows operating system in an existing service.
The cmdlet bases the virtual machine on the specified image.
The command specifies the *WaitForBoot* parameter.
Therefore, the cmdlet waits for the virtual machine to start.

### Example 2: Create a virtual machine that by using certificates
```
PS C:\>$certs = Get-ChildItem Cert:\CurrentUser\My
PS C:\> New-AzureQuickVM -Windows -ServiceName "MySvc1" -name "MyWinVM1" -ImageName "Image07" -Password "password" -AdminUserName "AdminMain" -WinRMCertificate $certs[0] -X509Certificates $certs[1], $certs[2] -WaitForBoot
```

The first command gets certificates from a store, and stores them in the $certs variable.

The second command creates a virtual machine that runs the Windows operating system in an existing service from an image.
By default, WinRM Https listener is enabled on the virtual machine.
The command specifies the *WaitForBoot* parameter.
Therefore, the cmdlet waits for the virtual machine to start.
The command uploads a WinRM Certificate and X509Certificates to the hosted service.

### Example 3: Create a virtual machine that runs the Linux operating system
```
PS C:\>New-AzureQuickVM -Linux -ServiceName "ContosoServiceLinux01" -Name "LinuxVirtualMachine01" -ImageName "LinuxImage01" -LinuxUser "RootMain" -Password "password" -Location "Central US"
```

This command creates a virtual machine that runs the Linux operating system from an image.
This command creates a service to host the new virtual machine.
The command specifies a location for the service.

### Example 4: Create a virtual machine and create a service to host the new virtual machine
```
PS C:\>$Locations = Get-AzureLocation
PS C:\> $Images = Get-AzureVMImage
PS C:\> New-AzureQuickVM -Windows -InstanceSize "Large" -ServiceName "ContosoService03" -Name " VirtualMachine25" -ImageName $images[4].imagename -Password "password" -AdminUsername "AdminMain" -Location $Locations[0].name
```

The first command gets locations by using the Get-AzureLocation cmdlet, and then stores them in the $Locations array variable.

The second command gets available images by using the Get-AzureVMImage cmdlet, and then stores them in the $Images array variable.

The final command creates a large virtual machine named VirtualMachine25.
The virtual machine runs the Windows operating system.
It is based on one of the images in $Images.
The command creates a service named ContosoService03 for the new virtual machine.
The service is in a location in $Locations.

### Example 5: Create a virtual machine that has a reserved IP name
```
PS C:\>$Locations = Get-AzureLocation
PS C:\> $Images = Get-AzureVMImage
PS C:\> New-AzureQuickVM -Windows -InstanceSize "Large" -ServiceName "ContosoService04" -Name "VirtualMachine27" -ImageName $Images[4].imagename -Password "password" -AdminUsername "AdminMain" -Location $Locations[0].name -ReservedIPName $ipName
```

The first command gets locations, and then stores them in the $Locations array variable.

The second command gets available images, and then stores them in the $Images array variable.

The final command creates a virtual machine named VirtualMachine27 based on one of the images in $Images.
The command creates a service in a location in $Locations.
The virtual machine has a reserved IP name, previously stored in the $ipName variable.

## PARAMETERS

### -AdminUsername
Specifies the user name of the Administrator account that this cmdlet creates on the virtual machine.

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

### -AffinityGroup
Specifies the affinity group for the virtual machine.
Specify this parameter or the *Location* parameter only if this cmdlet creates an Azure service for the virtual machine.

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

### -AvailabilitySetName
Specifies the name of the availability set in which this cmdlet creates the virtual machine.

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

### -Certificates
Specifies a list of certificates that this cmdlet uses to create the service.

```yaml
Type: CertificateSettingList
Parameter Sets: Windows
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

If the guest operating system is the Windows operating system, this cmdlet saves this data as a binary file that is named %SYSTEMDRIVE%\AzureData\CustomData.bin.

If the guest operating system is Linux, this cmdlet passes the data by using the ovf-env.xml file.
Installation copies that file to the /var/lib/waagent directory.
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

### -DisableGuestAgent
Indicates that this cmdlet disables the infrastructure as a service (IaaS) provision guest agent.

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

### -DisableWinRMHttps
Indicates that this cmdlet disables Windows Remote Management (WinRM) on HTTPS.
By default, WinRM is enabled over HTTPS.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsSettings
Specifies an array of DNS server objects that defines the DNS settings for the new deployment.
To create a **DnsServer** object, use the New-AzureDns cmdlet.

```yaml
Type: DnsServer[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableWinRMHttp
Indicates that this cmdlet enables WinRM over HTTP.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostCaching
Specifies the host caching mode for the operating system disk.
Valid values are: 

- ReadOnly
- ReadWrite

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

### -ImageName
Specifies the name of the disk image this cmdlet uses to create the operating system disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceSize
Specifies the size of the instance.
Valid values are: 

- ExtraSmall
- Small
- Medium
- Large
- ExtraLarge
- A5
- A6
- A7
- A8
- A9
- Basic_A0
- Basic_A1
- Basic_A2
- Basic_A3
- Basic_A4
- Standard_D1
- Standard_D2
- Standard_D3
- Standard_D4
- Standard_D11
- Standard_D12
- Standard_D13
- Standard_D14

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

### -Linux
Indicates that this cmdlet creates a Linux based virtual machine.

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
Specifies the user name of the Linux administrative account that this cmdlet creates on the virtual machine.

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

### -Location
Specifies the Azure datacenter that hosts the virtual machine.
If you specify this parameter, the cmdlet creates an Azure service in the specified location.
Specify this parameter or the *AffinityGroup* parameter only if this cmdlet creates an Azure service for the virtual machine.

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

### -MediaLocation
Specifies the Azure Storage location where this cmdlet creates the virtual machines disks.

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

### -Name
Specifies the name of the virtual machine that this cmdlet creates.

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

### -NoExportPrivateKey
Indicates that this configuration does not upload the private key.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWinRMEndpoint
Indicates that this cmdlet does not add a WinRM endpoint for the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password for the administrative account.

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

### -ReservedIPName
Specifies the reserved IP name.

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

### -ServiceName
Specifies the name of a new or existing Azure service to which this cmdlet adds the new virtual machine.

If you specify a new service, this cmdlets creates it.
To create a new service, you must specify the *Location* or *AffinityGroup* parameter.

If you specify an existing service, do not specify *Location* or *AffinityGroup*.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -SubnetNames
Specifies an array of names of subnet for the virtual machine.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VNetName
Specifies the name of a virtual network for the virtual machine.

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

### -WaitForBoot
Indicates that this cmdlet waits for the virtual machine to reach the state ReadyRole.
If the virtual machine reaches one of the following states, the cmdlet fails: FailedStartingVM, ProvisioningFailed, or ProvisioningTimeout.

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

### -Windows
Indicates that this cmdlet creates a Windows virtual machine.

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

### -WinRMCertificate
Specifies a certificate that this cmdlet associates to a WinRM endpoint.

```yaml
Type: X509Certificate2
Parameter Sets: Windows
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
Parameter Sets: Windows
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
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReverseDnsFqdn
Specifies the fully qualified domain name for reverse DNS look up.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureLocation](.\Get-AzureLocation.md)

[Get-AzureVMImage](.\Get-AzureVMImage.md)

[New-AzureDns](.\New-AzureDns.md)

