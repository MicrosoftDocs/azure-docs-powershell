---
title: Get started with Azure PowerShell | Microsoft Docs
description:
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.date: 03/22/2017
ms.author: sewhee
---
# Getting started with Azure PowerShell

Azure PowerShell is designed for managing and administering Azure resources from the command line,
and for building automation scripts that work against the Azure Resource Manager. This article
helps get you started using it, and teaches you the core concepts behind it.

This article assumes that you have already installed Azure PowerShell and loaded the module.

## Install Azure PowerShell
The first step is to make sure you have the latest version of the Azure PowerShell installed:

1. [Install Azure PowerShell](install-azurerm-ps.md).

2. To verify the installation was successful, run `Get-Module AzureRM` from your
   command line.

You should see the version number of the AzureRM module installed and loaded in your PowerShell
session.

## Log in to Azure

Sign on interactively:

1. Type `Login-AzureRmAccount`.  You will get dialog box asking for your Azure credentials.

2. Type the email address and password associated with your account. Azure authenticates and saves
   the credential information, and then closes the window.

Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and
manager the resources in your subscription.

## Create a resource group

Now that we've got everything set up, let's use Azure PowerShell to create resources within Azure.

First, create a Resource Group. Resource Groups in Azure provide a way to manage multiple resources
that you want to logically group together. For example, you might create a Resource Group for an
application or project and add a virtual machine, a database and a CDN service within it.

Let's create a resource group named "MyResourceGroup" in the westus2 region of Azure. To do so type
the following command:

```powershell
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

## Create a Windows Virtual Machine

Now that we have our resource group, let's create a Linux VM within it. To create a new VM we must
first create the other required resources and assign them to a configuration. When we can use that
configuration to create the VM.

### Create the required network resources

First we need to create a subnet configuration to be used with the virtual network creation
process. We also create a public IP address so that we can connect to this VM. We create a network
security group to secure access to the public address. Finally we create the virtual NIC using all
of the previous resources.

```powershell
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myVM"

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet -AddressPrefix 192.168.1.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$pip = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4

# Create an inbound network security group rule for port 3389
$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 3389 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup -SecurityRules $nsgRuleRDP

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -NetworkSecurityGroupId $nsg.Id
```

### Create the virtual machine

First we need a set of credentials for the OS.

```powershell
# Create user object
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

Now that we have the required resources we can create the VM. For this step, we create a VM
configuration object, then we use tje configuration to create the VM.

```powershell
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Windows -ComputerName $vmName -Credential $cred |
  Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

Now you have a Windows VM. You can log in and begin using your new VM.

## Listing deployed resources

You can use the `Get-AzureRmResource` cmdlet to list the resources running in Azure. The following
example shows the resources we just created in the new resource group.

```powershell
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```
Name                                              Location   ResourceType
----                                              --------   ------------
myWinVM_OsDisk_1_a3fb3fa77a1c4b4e9e44fd95a2850b45 westeurope Microsoft.Compute/disks
myWinVM                                           westeurope Microsoft.Compute/virtualMachines
myWinVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic                                             westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup                            westeurope Microsoft.Network/networkSecurityGroups
mypublicdns468205664                              westeurope Microsoft.Network/publicIPAddresses
MYvNET                                            westeurope Microsoft.Network/virtualNetworks
micromyresomywi032813340                          westeurope Microsoft.Storage/storageAccounts
```

## Clean up the deployment

To clean up your Azure account, you want to remove the resources we created in this example. You
can remove each resource, individually with the associated `Remove-*` cmdlet. However, the easiest
way is to remove the resource group. This will automatically remove all of the resources in the
group. Run the following command to remove the resource group, VM, and all related resources.

```powershell
Remove-AzureRmResourceGroup -Name myResourceGroup
```
You will be prompted to confirm that you want to remove the resource group.

```
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This can take several minutes to complete.

## Next steps

* [Login with Azure PowerShell](authenticate-azureps.md)
* [Manage Azure subscriptions with Azure PowerShell](manage-subscriptions-azureps.md)
* [Create service principals in Azure using Azure PowerShell](create-azure-service-principal-azureps.md)
* Read the Release notes about migrating from an older release:
  [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).
* Get help from the community:
  + [Azure forum on MSDN](http://go.microsoft.com/fwlink/p/?LinkId=320212)
  + [stackoverflow](http://go.microsoft.com/fwlink/?LinkId=320213)
