---
title: Query output of Azure PowerShell cmdlets
description: How to query for resources in Azure and format the results.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/10/2019
---
# Query output of Azure PowerShell 

The results of each Azure PowerShell cmdlet are an Azure PowerShell object. Even cmdlets that aren't explicitly `Get-` operations
might return a value that can be inspected, to give information about a resource that was created or modified. While most cmdlets
return a single object, some return an array that should be iterated through.

In almost all cases, you query output from Azure PowerShell with the [Select-Object](/powershell/module/Microsoft.PowerShell.Utility/Select-Object)
cmdlet, often abbreviated to `select`. Output can be filtered with [Where-Object](/powershell/module/Microsoft.PowerShell.Core/Where-Object), or its alias `where`.

## Select simple properties

In the default table format, Azure PowerShell cmdlets don't display all of their available properties. You can get the full properties by using the
[Format-List](/powershell/module/microsoft.powershell.utility/format-list) cmdlet, or by piping output to `Select-Object *`:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup | Select-Object *
```

```output
ResourceGroupName        : TESTGROUP
Id                       : /subscriptions/711d8ed1-b888-4c52-8ab9-66f07b87eb6b/resourceGroups/TESTGROUP/providers/Micro
                           soft.Compute/virtualMachines/TestVM
VmId                     : 711d8ed1-b888-4c52-8ab9-66f07b87eb6b
Name                     : TestVM
Type                     : Microsoft.Compute/virtualMachines
Location                 : westus2
LicenseType              :
Tags                     : {}
AvailabilitySetReference :
DiagnosticsProfile       :
Extensions               : {}
HardwareProfile          : Microsoft.Azure.Management.Compute.Models.HardwareProfile
InstanceView             :
NetworkProfile           : Microsoft.Azure.Management.Compute.Models.NetworkProfile
OSProfile                : Microsoft.Azure.Management.Compute.Models.OSProfile
Plan                     :
ProvisioningState        : Succeeded
StorageProfile           : Microsoft.Azure.Management.Compute.Models.StorageProfile
DisplayHint              : Compact
Identity                 :
Zones                    : {}
FullyQualifiedDomainName :
AdditionalCapabilities   :
RequestId                : 711d8ed1-b888-4c52-8ab9-66f07b87eb6b
StatusCode               : OK
```

Once you know the names of the properties that you're interested in, you can use those property names with `Select-Object` to get them directly:

```azurepowershell-interactive
Get-AzVM -Name TestVM -ResourceGroupName TestGroup | Select-Object Name,VmId,ProvisioningState
```

```output
Name   VmId                                 ProvisioningState
----   ----                                 -----------------
TestVM 711d8ed1-b888-4c52-8ab9-66f07b87eb6b Succeeded
```

Output from using `Select-Object` is always formatted to display the requested information. To learn about using formatting as part
of querying cmdlet results, see [Format Azure PowerShell cmdlet output](formatting-output.md).

## Select nested properties

Some properties in Azure PowerShell cmdlet output use nested objects, like the `StorageProfile` property
of `Get-AzVM` output. To get a value from a nested property, provide a display name and the full path to the value you
want to inspect as part of a dictionary argument to `Select-Object`:

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup | `
    Select-Object Name,@{Name="OSType"; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```output
Name     OSType
----     ------
TestVM    Linux
TestVM2   Linux
WinVM   Windows
```

Each dictionary argument selects one property from the object. The property to extract must be part
of an expression.

## Filter results 

The `Where-Object` cmdlet allows you to filter the result based on any property value, including
nested properties. The next example shows how to use `Where-Object` to find the Linux VMs in a resource group.

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup | `
    Where-Object {$_.StorageProfile.OSDisk.OSType -eq "Linux"}
```

```output
ResourceGroupName    Name Location          VmSize OsType        NIC ProvisioningState Zone
-----------------    ---- --------          ------ ------        --- ----------------- ----
TestGroup          TestVM  westus2 Standard_D2s_v3  Linux  testvm299         Succeeded
TestGroup         TestVM2  westus2 Standard_D2s_v3  Linux testvm2669         Succeeded
```

You can pipe the results of `Select-Object` and `Where-Object` to each other. For performance purposes, it's always recommended to put the `Where-Object` operation before `Select-Object`:

```azurepowershell-interactive
Get-AzVM -ResourceGroupName TestGroup | `
    Where-Object {$_.StorageProfile.OsDisk.OsType -eq "Linux"} | `
    Select-Object Name,VmID,ProvisioningState
```

```output
Name    VmId                                 ProvisioningState
----    ----                                 -----------------
TestVM  711d8ed1-b888-4c52-8ab9-66f07b87eb6  Succeeded
TestVM2 cbcee769-dd78-45e3-a14d-2ad11c647d0  Succeeded
```
