---
title: Querying for Azure resources and formatting results | Microsoft Docs
description: How to query for resources in Azure and format the results.
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

# Querying for Azure resources

## How queries work in PowerShell

There is no special query language required to query resources using Azure PowerShell. In
PowerShell, cmdlet names take the form of **_Verb-Noun_**. The cmdlets using the verb **_Get_** are
the query cmdlets. The cmdlet nouns are the types of Azure resources that are acted upon by the
cmdlet verbs.

To get a list of Verbs used in the AzureRM module, use the following commands:

```powershell
Get-Command -Module AzureRM  | Select-Object -Unique Verb
```

```
Verb
----
Add
Backup
ConvertTo
Disable
Edit
Enable
Export
Find
Get
Grant
Import
...
```

The previous output is truncated for brevity in this example. There are 40 Verbs used in the
AzureRM module.


The following commands get a list of the 676 Nouns defined in the AzureRM module.

```powershell
Get-Command -Module AzureRM | Select-Object -Unique Noun
```

After reviewing the list of Nouns, you may be interested in seeing what Verbs can be used with Azure VMs. The following examples shows how to get a list of cmdlets that operate on Azure VMs.

```powershell
Get-Command -Module AzureRM -Noun AzureRMVM
```

```
CommandType Name              Version Source
----------- ----              ------- ------
Cmdlet      Get-AzureRmVM     3.7.0   AzureRM
Cmdlet      New-AzureRmVM     3.7.0   AzureRM
Cmdlet      Remove-AzureRmVM  3.7.0   AzureRM
Cmdlet      Restart-AzureRmVM 3.7.0   AzureRM
Cmdlet      Set-AzureRmVM     3.7.0   AzureRM
Cmdlet      Start-AzureRmVM   3.7.0   AzureRM
Cmdlet      Stop-AzureRmVM    3.7.0   AzureRM
Cmdlet      Update-AzureRmVM  3.7.0   AzureRM
```

Use the `Get-AzureRmVM` cmdlet to query for a list of VMs in your account.

```powershell
Get-AzureRmVM
```

The default output is automatically formatted as a table.

```
ResourceGroupName          Name   Location          VmSize  OsType              NIC ProvisioningState
-----------------          ----   --------          ------  ------              --- -----------------
MYWESTEURG        MyUnbuntu1610 westeurope Standard_DS1_v2   Linux myunbuntu1610980         Succeeded
MYWESTEURG          MyWin2016VM westeurope Standard_DS1_v2 Windows   mywin2016vm880         Succeeded
```

For more information about formatting output, see [Formatting query results](formatting-output.md).