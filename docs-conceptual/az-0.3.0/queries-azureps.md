---
title: Query output of Azure PowerShell cmdlets
description: How to query for resources in Azure and format the results.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/11/2018
---
# Query output of Azure PowerShell cmdlets

Querying in PowerShell can be completed by using built-in cmdlets. In
PowerShell, cmdlet names take the form of **_Verb-Noun_**. The cmdlets using the verb **_Get_** are
the query cmdlets. The cmdlet nouns are the types of Azure resources that are acted upon by the
cmdlet verbs.

## Select simple properties

Azure PowerShell has default formatting defined for each cmdlet. The most common properties for
each resource type are displayed in a table or list format automatically. For more information
about formatting output, see [Formatting query results](formatting-output.md).

Use the `Get-AzureRmVM` cmdlet to query for a list of VMs in your account.

```azurepowershell-interactive
Get-AzureRmVM
```

The default output is automatically formatted as a table.

```output
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

The `Select-Object` cmdlet can be used to select the specific properties that are interesting to you.

```azurepowershell-interactive
Get-AzureRmVM | Select Name,ResourceGroupName,Location
```

```output
Name          ResourceGroupName Location
----          ----------------- --------
MyUnbuntu1610 MYWESTEURG        westeurope
MyWin2016VM   MYWESTEURG        westeurope
```

## Select complex nested properties

If the property you want is nested in the JSON output, you need to supply the full
path to the property. The following example shows how to select the VM Name and the OS type
from the `Get-AzureRmVM` cmdlet.

```azurepowershell-interactive
Get-AzureRmVM | Select Name,@{Name='OSType'; Expression={$_.StorageProfile.OSDisk.OSType}}
```

```output
Name           OSType
----           ------
MyUnbuntu1610   Linux
MyWin2016VM   Windows
```

## Filter results with the Where-Object cmdlet

The `Where-Object` cmdlet allows you to filter the result based on any property value. In the
following example, the filter selects only VMs that have the text "RGD" in their name.

```azurepowershell-interactive
Get-AzureRmVM | Where ResourceGroupName -like RGD* | Select ResourceGroupName,Name
```

```output
ResourceGroupName  Name
-----------------  ----
RGDEMO001          KBDemo001VM
RGDEMO001          KBDemo020
```

With the next example, the results will return the VMs that have the vmSize 'Standard_DS1_V2'.

```azurepowershell-interactive
Get-AzureRmVM | Where vmSize -eq Standard_DS1_V2
```

```output
ResourceGroupName          Name     Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----     --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610   westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM   westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```