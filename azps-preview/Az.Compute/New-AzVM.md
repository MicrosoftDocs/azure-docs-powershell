---
document type: cmdlet
external help file: Microsoft.Azure.Azclips.Cmdlets.Compute.dll-Help.xml
HelpUri: ''
Locale: en-US
Module Name: Az.Compute
ms.date: 10/13/2026
PlatyPS schema version: 2024-05-01
title: New-AzVM
---

# New-AzVM

## SYNOPSIS

Create a virtual machine with a new network interface or attach existing network interfaces.

## SYNTAX

### NewNetworkInterface (Default)

```
New-AzVM -Name <string> -Location <string> -ResourceGroupName <string> -VmSize <string>
 -AdminUsername <string> -AdminPassword <string> -NetworkInterfaceName <string>
 [-SubscriptionId <string>] [-Image <string>] [-SecurityType <string>]
 [-OSDiskSecurityEncryptionType <string>] [-OSDiskSecureVMDiskEncryptionSet <string>]
 [-EnableSecureBoot <bool>] [-EnableVtpm <bool>] [-VirtualNetworkName <string>] [-SecurityGroupName <string>]
 [-SubnetName <string>] [-NetworkInterfaceDeleteOption <string>] [-SubnetNames <string[]>]
 [-SubnetAddressPrefixes <string[][]>] [-AddressPrefixes <string[]>] [-AcceleratedNetworking]
 [-PublicIpAddressName <string>] [-Tags <hashtable>] [-Profile <string>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ExistingNetworkInterface

```
New-AzVM -Name <string> -Location <string> -ResourceGroupName <string> -VmSize <string>
 -AdminUsername <string> -AdminPassword <string> -NetworkInterfaceId <string[]>
 [-SubscriptionId <string>] [-Image <string>] [-SecurityType <string>]
 [-OSDiskSecurityEncryptionType <string>] [-OSDiskSecureVMDiskEncryptionSet <string>]
 [-EnableSecureBoot <bool>] [-EnableVtpm <bool>] [-NetworkInterfaceDeleteOption <string>] [-Tags <hashtable>]
 [-Profile <string>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## ALIASES

## DESCRIPTION

Creates a virtual machine using either the default `NewNetworkInterface` parameter set or the `ExistingNetworkInterface` parameter set.
The default parameter set creates a network interface and creates or reuses its virtual network, subnet, network security group, and public IP address according to the supplied parameters.
With `-NetworkInterfaceId`, the existing-NIC parameter set attaches the supplied network interfaces without creating a virtual network, network security group, public IP address, or network interface; the first network interface is primary.
In the default parameter set, the network security group is named after the virtual machine with an `NSG` suffix (for example `myvmNSG`), created or, if it already exists, updated.
A network security group this command creates has one inbound rule for the image's operating system, allowing traffic from any source: `rdp` (TCP port 3389) for Windows or `default-allow-ssh` (TCP port 22) for Linux.
Use `-SecurityGroupName` to choose the network security group by name or resource ID, or pass an empty string to create none.
Use `-SubnetName` to select one subnet by name from `-VirtualNetworkName`, or pass a full subnet resource ID.
Use `-NetworkInterfaceId` instead of the network-creation parameters to attach one or more existing network interfaces; the first is primary.
Use `-NetworkInterfaceDeleteOption` to choose whether attached network interfaces are deleted or detached when the virtual machine is deleted.
In the default parameter set, the public IP address is a Standard, static address named after the virtual machine with a `PublicIP` suffix (for example `myvmPublicIP`), created or, if it already exists, updated.
Use `-PublicIpAddressName` to choose the public IP address by name or resource ID, or pass an empty string to create none.
Use this command when you want a one-shot VM deployment without composing the underlying resources individually.

## EXAMPLES

### Create a VM with its networking stack

Provision a `Standard_D2s_v3` virtual machine named `myvm` in `myrg` (East US) along with a fresh virtual network (`myvnet`), network interface (`mynic`), and network security group (`myvmNSG`, which allows inbound RDP).
Assign `$adminPassword` from a secure source in your own pipeline before invoking the cmdlet (the value below is a literal placeholder, not a real password).

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
New-AzVM -SubscriptionId 00000000-0000-0000-0000-000000000000 -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -Image MicrosoftWindowsServer:WindowsServer:2022-datacenter-azure-edition:latest -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceName mynic -VirtualNetworkName myvnet
```

### Create a VM that uses an existing network security group

Provision the same stack, but attach the existing network security group `mynsg` in `myrg` instead of creating one.
The network security group is attached as-is; its rules are not changed.

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
New-AzVM -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceName mynic -VirtualNetworkName myvnet -SecurityGroupName mynsg
```

### Create a VM with a named public IP address

Provision the same stack, but name the public IP address `myvm-ip`.
If a public IP address named `myvm-ip` already exists in `myrg`, it is attached as-is instead of being created.

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
New-AzVM -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceName mynic -VirtualNetworkName myvnet -PublicIpAddressName myvm-ip
```

### Create a Trusted Launch VM with secure boot disabled

Provision a Trusted Launch VM and explicitly disable secure boot while keeping vTPM enabled.

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
New-AzVM -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -Image MicrosoftWindowsServer:WindowsServer:2022-datacenter-azure-edition:latest -SecurityType TrustedLaunch -EnableSecureBoot $false -EnableVtpm $true -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceName mynic -VirtualNetworkName myvnet
```

### Create a VM without a public IP address

Pass an empty string to `-PublicIpAddressName` to provision the stack without a public IP address.
The virtual machine is then reachable only from inside its virtual network.

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
New-AzVM -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceName mynic -VirtualNetworkName myvnet -PublicIpAddressName ''
```

### Create a VM in a selected subnet

Create the network interface in the existing `app` subnet of `myvnet`. A full subnet resource ID
can be supplied instead of the subnet name.

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
New-AzVM -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceName mynic -VirtualNetworkName myvnet -SubnetName app
```

### Create a VM with existing network interfaces

Attach two existing network interfaces. The first is primary, and both interfaces are detached
when the virtual machine is deleted.

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
$nicIds = @(
    '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Network/networkInterfaces/my-primary-nic',
    '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myrg/providers/Microsoft.Network/networkInterfaces/my-secondary-nic'
)
New-AzVM -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceId $nicIds -NetworkInterfaceDeleteOption Detach
```

### Create a VM with tags

Provision the same stack and tag the virtual machine, network interface, virtual network, network security group, and public IP address with `env=prod` and `owner=team-a`.

```powershell
$adminPassword = 'P@ssw0rd-replace-me!'
New-AzVM -Name myvm -Location eastus -ResourceGroupName myrg -VmSize Standard_D2s_v3 -AdminUsername azureuser -AdminPassword $adminPassword -NetworkInterfaceName mynic -VirtualNetworkName myvnet -Tags @{ env = 'prod'; owner = 'team-a' }
```

## PARAMETERS

### -AcceleratedNetworking

Enables accelerated networking on the network interface created for the virtual machine. Off
unless set; the chosen VM size must support accelerated networking.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AddressPrefixes

Address prefixes for the virtual network.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AdminPassword

The administrator password.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AdminUsername

The administrator username.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- cf
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Image

The marketplace image URN to use.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases:
- ImageName
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableSecureBoot

Enables or disables secure boot in the virtual machine UEFI settings.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -EnableVtpm

Enables or disables vTPM in the virtual machine UEFI settings.

```yaml
Type: System.Nullable`1[System.Boolean]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Location

Location for all resources.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Name

The name of the virtual machine.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -NetworkInterfaceDeleteOption

Specifies what happens to attached network interfaces when the virtual machine is deleted. The
value applies to every interface supplied through `-NetworkInterfaceId`, or to the interface
created through `-NetworkInterfaceName`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- Delete
- Detach
HelpMessage: ''
```

### -NetworkInterfaceId

Names or resource IDs of existing network interfaces to attach. Names are resolved in the VM's
resource group. The first interface is primary. This parameter cannot be combined with the
network-interface creation parameters.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ExistingNetworkInterface
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -NetworkInterfaceName

The network interface name to create. This parameter cannot be combined with
`-NetworkInterfaceId`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -OSDiskSecureVMDiskEncryptionSet

Disk Encryption Set name or resource ID for customer-managed ConfidentialVM OS disk encryption.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -OSDiskSecurityEncryptionType

Security encryption type for the OS managed disk. Required for ConfidentialVM.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- VMGuestStateOnly
- DiskWithVMGuestState
- NonPersistedTPM
HelpMessage: ''
```

### -Profile

Name of a saved profile to use for this call instead of the currently-active one. Manage profiles with `Set-AzProfile` / `Get-AzProfile`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -PublicIpAddressName

Name of the public IP address to create (default: '{vm}PublicIP') or of an existing one to attach.
Can also reference an existing public IP by resource ID, or specify "" for none.

When omitted, a public IP address named after the virtual machine with a `PublicIP` suffix is created, or updated if it already exists.
A name is looked up in the resource group: an existing public IP address is attached as-is, otherwise one is created.
A resource ID must reference an existing public IP address, which is attached as-is.
New public IP addresses use the Standard SKU with static allocation, in the virtual machine's location.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ResourceGroupName

The resource group name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SecurityGroupName

Name of the network security group to create (default: '{vm}NSG') or of an existing one to attach.
Can also reference an existing NSG by resource ID, or specify "" for none.

When omitted, a network security group named after the virtual machine with an `NSG` suffix is created, or updated if it already exists.
A name is looked up in the resource group: an existing network security group is attached as-is, otherwise one is created.
A resource ID must reference an existing network security group, which is attached as-is.
A network security group this command creates has one inbound rule for the image's operating system, allowing traffic from any source: `rdp` (TCP port 3389) for Windows or `default-allow-ssh` (TCP port 22) for Linux.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SecurityType

Security type for the virtual machine.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues:
- TrustedLaunch
- ConfidentialVM
- Standard
HelpMessage: ''
```

### -SubnetAddressPrefixes

Address prefixes for each subnet.

```yaml
Type: System.String[][]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubnetName

Name or full resource ID of the subnet for the new network interface. A subnet name is resolved
under `-VirtualNetworkName`. A full subnet resource ID bypasses virtual-network creation.
Do not combine this parameter with `-SubnetNames` or `-NetworkInterfaceId`.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubnetNames

Names of the subnets.

```yaml
Type: System.String[]
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -SubscriptionId

Azure Subscription Id. Defaults to the active profile's subscription.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Tags

Tags to apply to the virtual machine and to every network resource the command creates.
Resources the command only attaches keep their own tags, such as network interfaces supplied through `-NetworkInterfaceId`, the virtual network of an existing subnet selected with `-SubnetName`, or an existing network security group or public IP address.

```yaml
Type: System.Collections.Hashtable
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -VirtualNetworkName

The virtual network name to create or use when `-SubnetName` is a subnet name.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: NewNetworkInterface
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -VmSize

The size of the virtual machine.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: true
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases:
- wi
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Azclips.Extensions.Compute.Models.VirtualMachine

The newly-created `VirtualMachine` object, including its assigned ARM resource ID, provisioning state, size, and network configuration, plus the `PowerState`, `PublicIps`, `Fqdns`, `PrivateIps`, and `MacAddresses` detail fields.
`Fqdns` is empty unless an attached existing public IP address has a DNS name label; public IP addresses this command creates have none.
`PublicIps` is empty when no public IP address is attached, including when `-PublicIpAddressName` is an empty string in the default parameter set or the supplied existing NICs have no public IP addresses.

## NOTES

Generated help for compute.
Networking resources are created or reused only in the default `NewNetworkInterface` parameter set.
The `ExistingNetworkInterface` parameter set uses the existing NICs and their networking configuration without creating networking resources.

## RELATED LINKS


- [Online Version]()
