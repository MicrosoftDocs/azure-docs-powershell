---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Add-AzureDataDisk.md
schema: 2.0.0
---

# New-AzureVM

## SYNOPSIS
Creates an Azure virtual machine.

## SYNTAX

### ExistingService (Default)
```
New-AzureVM -ServiceName <String> [-DeploymentLabel <String>] [-DeploymentName <String>] [-VNetName <String>]
 [-DnsSettings <DnsServer[]>] [-InternalLoadBalancerConfig <InternalLoadBalancerConfig>] -VMs <PersistentVM[]>
 [-WaitForBoot] [-ReservedIPName <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### CreateService
```
New-AzureVM -ServiceName <String> [-Location <String>] [-AffinityGroup <String>] [-ServiceLabel <String>]
 [-ReverseDnsFqdn <String>] [-ServiceDescription <String>] [-DeploymentLabel <String>]
 [-DeploymentName <String>] [-VNetName <String>] [-DnsSettings <DnsServer[]>]
 [-InternalLoadBalancerConfig <InternalLoadBalancerConfig>] -VMs <PersistentVM[]> [-WaitForBoot]
 [-ReservedIPName <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureVM** cmdlet adds a new virtual machine to an existing Azure service, or creates a virtual machine and service in the current subscription if either the *Location* or *AffinityGroup* is specified.

## EXAMPLES

### Example 1: Create a virtual machine for a Windows configuration
```
PS C:\>New-AzureVMConfig -Name "VirtualMachine07" -InstanceSize ExtraSmall -ImageName (Get-AzureVMImage)[4].ImageName | Add-AzureProvisioningConfig -Windows -Password $adminPassword -AdminUsername PsTestAdmin | New-AzureVM -ServiceName "ContosoService" -AffinityGroup "Contoso" -WaitForBoot
```

This command creates a provisioning configuration based on a virtual machine configuration for the Windows operating system, and uses it to create a virtual machine in a specified affinity group.

### Example 2: Create a virtual machine for a Linux configuration
```
PS C:\>New-AzureVMConfig -Name "SUSEVM02" -InstanceSize ExtraSmall -ImageName (Get-AzureVMImage)[7].ImageName | Add-AzureProvisioningConfig -Linux -LinuxUser "RootMain" -Password "password" -AdminUsername PsTestAdmin | New-AzureVM
```

This command creates a provisioning configuration based on a virtual machine configuration for Linux, and uses it to create a virtual machine in a specified affinity group.

### Example 3: Create a virtual machine and add a data disk
```
PS C:\>$Images = Get-AzureVMImage
PS C:\> $Image = $Images[4]
PS C:\> $VirtualMachine02 = New-AzureVMConfig -Name "VirtualMachine02" -InstanceSize ExtraSmall -ImageName $myImage.ImageName | Add-AzureProvisioningConfig -Windows -Password "password" | Add-AzureDataDisk -CreateNew -DiskSizeInGB 50 -DiskLabel "DataDisk50" -LUN 0
```

The first two commands get available images by using the Get-AzureVMImage cmdlet, and stores one of them in the $Image variable.

This command creates a provisioning configuration based on a virtual machine configuration for the Windows operating system, and uses it to create a virtual machine with an Azure data disk.

### Example 4: Create a virtual machine with a reserved IP address
```
PS C:\>New-AzureVMConfig -Name "VirtualMachine06" -InstanceSize ExtraSmall -ImageName (Get-AzureVMImage)[4].ImageName | Add-AzureProvisioningConfig -Windows -Password $adminPassword -AdminUsername "AdminMain" | New-AzureVM -ServiceName "ContosoService02" -AffinityGroup "Contoso" -ReservedIPName $ipName
```

This command creates a provisioning configuration based on a virtual machine configuration for the Windows operating system, and uses it to create a virtual machine with a reserved IP address.

## PARAMETERS

### -ServiceName
Specifies the new or existing service name.

If the service does not exist, this cmdlet creates it for you.
Use the *Location* or *AffinityGroup* parameter to specify where to create the service.

If the service exists, the *Location* or *AffinityGroup* parameter is not needed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeploymentLabel
Specifies a label for the deployment.

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

### -DeploymentName
Specifies a deployment name.
If not specified, this cmdlet uses the service name as the deployment name.

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

### -VNetName
Specifies the virtual network name where this cmdlet deploys the virtual machine.

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

### -DnsSettings
Specifies a DNS Server object that defines the DNS settings for the new deployment.

```yaml
Type: DnsServer[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InternalLoadBalancerConfig
Specifies an internal load balancer.
This parameter is not used.

```yaml
Type: InternalLoadBalancerConfig
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMs
Specifies a list of virtual machine objects to create.

```yaml
Type: PersistentVM[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WaitForBoot
Specifies that this cmdlet waits for the virtual machine to reach the **ReadyRole** state.
This cmdlet fails if the virtual machine falls in one of the following states while waiting: FailedStartingVM, ProvisioningFailed, ProvisioningTimeout.

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

### -ReservedIPName
Specifies the name of the reserved IP address.

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

### -Location
Specifies the location that hosts the new service.
If the service already exists, do not specify this parameter.

```yaml
Type: String
Parameter Sets: CreateService
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AffinityGroup
Specifies the Azure affinity group in which the cloud service resides.
This parameter is required only when this cmdlet creates a cloud service.

```yaml
Type: String
Parameter Sets: CreateService
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceLabel
Specifies a label for the new service.

```yaml
Type: String
Parameter Sets: CreateService
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseDnsFqdn
Specifies the fully-qualified domain name for reverse DNS.

```yaml
Type: String
Parameter Sets: CreateService
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceDescription
Specifies a description for the new service.

```yaml
Type: String
Parameter Sets: CreateService
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

[Add-AzureDataDisk](.\Add-AzureDataDisk.md)

[Add-AzureProvisioningConfig](.\Add-AzureProvisioningConfig.md)

[Get-AzureVMImage](.\Get-AzureVMImage.md)

[New-AzureVMConfig](.\New-AzureVMConfig.md)

