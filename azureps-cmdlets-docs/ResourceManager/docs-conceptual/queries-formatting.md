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
ms.date: 03/06/2017
ms.author: sewhee
---

# Querying for Azure resources and formatting results

## Understanding how queries work in PowerShell

There is no special query language required to query resources using Azure PowerShell. In
PowerShell, cmdlet names take the form of _Verb-Noun_. The cmdlets using the verb _Get_ are the
query cmdlets. The cmdlet nouns are the types of Azure resources that are acted upon by the cmdlet
verbs.

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

The previous output is truncated for brevity in this example. As shown in the following example,
there are 40 Verbs used in the AzureRM module.

```powershell
Get-Command -Module AzureRM  | Select-Object -Unique Verb | Measure-Object
```

```
Count    : 40
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

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

## Formatting query results

By default, PowerShell has predefined formatting of output. So, in most cases, you don't have to do
anything special to get nicely formatted output. PowerShell has several formatting and conversion
cmdlets to help you present the output differently.

| Formatting    | Conversion     |
|---------------|----------------|
| Format-Custom | ConvertTo-Csv  |
| Format-List   | ConvertTo-Html |
| Format-Table  | ConvertTo-Json |
| Format-Wide   | ConvertTo-Xml  |

Take, for example, the simple query for a list of VMs.

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

Now lets use PowerShell to select specific values and covert that output to CSV format, for easy
import into a database or spreadsheet.

```powershell
Get-AzureRmVM | Select-Object ResourceGroupName,Id,VmId,Name,Location,ProvisioningState | ConvertTo-Csv -NoTypeInformation
```

```
"ResourceGroupName","Id","VmId","Name","Location","ProvisioningState"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyUnbuntu1610","33422f9b-e339-4704-bad8-dbe094585496","MyUnbuntu1610","westeurope","Succeeded"
"MYWESTUERG","/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/MYWESTUERG/providers/Microsoft.Compute/virtualMachines/MyWin2016VM","4650c755-fc2b-4fc7-a5bc-298d5c00808f","MyWin2016VM","westeurope","Succeeded"
```