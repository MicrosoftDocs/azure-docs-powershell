---
title: Get started with Azure PowerShell | Microsoft Docs
description: This is a running history of changes made to Azure PowerShell in each release.
services: azure
author: sdwheeler
manager: carmonm
ms.product: azure
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.date: 03/06/2017
ms.author: sewhee
---
# Getting started with Azure PowerShell

You can run the cmdlets from the standard Windows PowerShell console, or from PowerShell Integrated
Scripting Environment (ISE). The cmdlets need your subscription information so they can manage your
services.

This article assumes that you have already installed Azure PowerShell and loaded the module.

## Signing on to Azure

Sign on interactively:

1. Type `Login-AzureRmAccount`

2. Type the email address and password associated with your account. Azure authenticates and saves
   the credential information, and then closes the window.

--OR--

Sign into your work or school account:

```powershell
$cred = Get-Credential
Login-AzureRmAccount -Credential $cred
```

> [!NOTE]
> This non-interactive log in method only works with a work or school account. A work or
> school account is a user that is managed by your work or school, and defined in the Azure Active
> Directory instance for your work or school.
>
> For more information on signing up for Microsoft Azure with a work or school account, see [Sign up
> for Microsoft Azure as an Organization](/azure/active-directory/sign-up-organization.md).
>
> For more information about authentication and subscription management in Azure, see
> [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure.md).

Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and
manager the resources in your subscription.

## Create a resource group

A resource group is a container that holds related resources for an Azure solution. The resource
group can include all the resources for the solution, or only those resources that you want to
manage as a group. Resource groups can be used to manage role-based access controls (RBAC) for a
group of resources. For example, in your solution, you may want separate resource groups for VMs
and Virtual Networks so that you can assign RBAC permissions to different users for different
roles.

```powershell
New-AzureRmResourceGroup -Name 'MySouthCentralUSRG' -Location 'southcentralus'
```

```
ResourceGroupName : MySouthCentralUSRG
Location          : southcentralus
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MySouthCentralUSRG
```

## Create a storage account

An Azure storage account provides a unique namespace to store and access your Azure Storage data
objects. All objects in a storage account are billed together as a group. By default, the data in
your account is available only to you, the account owner.

The following example creates a general-purpose storage account that supports storing Blobs,
Tables, Queues, Files and Disks.

```powershell
$parameters = @{
  ResourceGroupName="myresourcegroup"
  AccountName="mystorageaccount"
  Location="westeurope"
  SkuName="Standard_GRS"
  Kind="Storage"
}
New-AzureRmStorageAccount @parameters
```

## Associate a Storage Account in your session

```powershell
Set-AzureRmCurrentStorageAccount -ResourceGroupName "mysouthcentralusrg" -StorageAccountName "mysouthcentstorage"
Get-AzureRmContext
```

```
Environment           : AzureCloud
Account               : username@contoso.com
TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
SubscriptionId        : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
SubscriptionName      : Microsoft Azure Internal Consumption
CurrentStorageAccount : mysouthcentstorage
```

To view a list of what is currently contained in the storage account:

```powershell
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

```
ICloudBlob        : Microsoft.WindowsAzure.Storage.Blob.CloudPageBlob
BlobType          : PageBlob
Length            : 614912
ContentType       : image/bmp
LastModified      : 3/7/2017 11:45:15 PM +00:00
SnapshotTime      :
ContinuationToken :
Context           : Microsoft.WindowsAzure.Commands.Common.Storage.LazyAzureStorageContext
Name              : MyWin2016VM.12345678-9abc-def0-1234-56789abcedf0.screenshot.bmp

ICloudBlob        : Microsoft.WindowsAzure.Storage.Blob.CloudPageBlob
BlobType          : PageBlob
Length            : 614912
ContentType       : image/bmp
LastModified      : 3/7/2017 11:44:57 PM +00:00
SnapshotTime      :
ContinuationToken :
Context           : Microsoft.WindowsAzure.Commands.Common.Storage.LazyAzureStorageContext
Name              : MyUnbuntu1610.12345678-9abc-def0-1234-56789abcedf0.screenshot.bmp

ICloudBlob        : Microsoft.WindowsAzure.Storage.Blob.CloudPageBlob
BlobType          : PageBlob
Length            : 56832
ContentType       : text/plain
LastModified      : 3/7/2017 11:16:57 PM +00:00
SnapshotTime      :
ContinuationToken :
Context           : Microsoft.WindowsAzure.Commands.Common.Storage.LazyAzureStorageContext
Name              : MyUnbuntu1610.12345678-9abc-def0-1234-56789abcedf0.serialconsole.log

ICloudBlob        : Microsoft.WindowsAzure.Storage.Blob.CloudPageBlob
BlobType          : PageBlob
Length            : 136367309312
ContentType       : application/octet-stream
LastModified      : 3/7/2017 11:45:18 PM +00:00
SnapshotTime      :
ContinuationToken :
Context           : Microsoft.WindowsAzure.Commands.Common.Storage.LazyAzureStorageContext
Name              : MyWin2016VM20170307125106.vhd

ICloudBlob        : Microsoft.WindowsAzure.Storage.Blob.CloudPageBlob
BlobType          : PageBlob
Length            : 32212255232
ContentType       : application/octet-stream
LastModified      : 3/7/2017 11:45:20 PM +00:00
SnapshotTime      :
ContinuationToken :
Context           : Microsoft.WindowsAzure.Commands.Common.Storage.LazyAzureStorageContext
Name              : MyUnbuntu161020170307141436.vhd
```

### List Virtual Machines

```powershell
Get-AzureRmVM
```

```
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

### List Virtual Networks

```powershell
Get-AzureRmVirtualNetwork
```

```
Name                   : MyWestEURG-vnet
ResourceGroupName      : MyWestEURG
Location               : westeurope
Id                     : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyWestEURG/providers/Microsoft.Network/virtualNetworks/MyWestEURG-vnet
Etag                   : W/"12345678-9abc-def0-1234-56789abcedf0"
ResourceGuid           : 79ba0a1a-a1a2-4491-822b-2ef874b1a628
ProvisioningState      : Succeeded
Tags                   :
AddressSpace           : {
                           "AddressPrefixes": [
                             "10.0.0.0/24"
                           ]
                         }
DhcpOptions            : null
Subnets                : [
                           {
                             "Name": "default",
                             "Etag": "W/\"12345678-9abc-def0-1234-56789abcedf0\"",
                             "Id": "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyWestEURG/providers/Microsoft.Network/virtualNetworks/MyWestEURG-vnet/subnets/default",
                             "AddressPrefix": "10.0.0.0/24",
                             "IpConfigurations": [
                               {
                                 "Id": "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyWestEURG/providers/Microsoft.Network/networkInterfaces/mywin2016vm880/ipConfigurations/ipconfig1"
                               },
                               {
                                 "Id": "/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MyWestEURG/providers/Microsoft.Network/networkInterfaces/myunbuntu1610980/ipConfigurations/ipconfig1"
                               }
                             ],
                             "ResourceNavigationLinks": [],
                             "ProvisioningState": "Succeeded"
                           }
                         ]
VirtualNetworkPeerings : []
```

### List Azure locations

```powershell
Get-AzureRmLocation | Select-Object Location
```

```
Location
--------
eastasia
southeastasia
centralus
eastus
eastus2
westus
northcentralus
southcentralus
northeurope
westeurope
japanwest
japaneast
brazilsouth
australiaeast
australiasoutheast
southindia
centralindia
westindia
canadacentral
canadaeast
uksouth
ukwest
westcentralus
westeurope2
koreacentral
koreasouth
```
