---
title: Run Azure PowerShell cmdlets in PowerShell Jobs
description: Learn how to run Azure PowerShell cmdlets in parallel or as background tasks, using -AsJob and Start-Job.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/21/2019
---

# Run Azure PowerShell cmdlets in PowerShell Jobs

Azure PowerShell depends on connecting to an Azure cloud and waiting for responses, so most
of these cmdlets block your PowerShell session until they get a response from the cloud.
Powershell Jobs let you run cmdlets in the background or do multiple tasks on Azure at once,
from inside a single PowerShell session.

This article is a brief overview of how to run Azure PowerShell cmdlets as PowerShell Jobs and check
for completion. Running commands in Azure PowerShell requires the use of Azure PowerShell contexts,
which are covered in detail in [Azure contexts and sign-in credentials](context-persistence.md).
To learn more about PowerShell Jobs, see [About PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

## Azure contexts with PowerShell jobs

PowerShell Jobs are run as separate processes without an attached PowerShell session, so your Azure credentials
must be shared with them. Credentials are passed as Azure context objects, using one of these methods:

* Automatic context persistence. Context persistence is enabled by default and preserves your sign-in information across
  multiple sessions. With context persistence enabled, the current Azure context is passed to the new process:

  ```azurepowershell-interactive
  Enable-AzContextAutosave # Enables context autosave if not already on
  $creds = Get-Credential
  $job = Start-Job { param($vmadmin) New-AzVM -Name MyVm -Credential $vmadmin } -ArgumentList $creds
  ```

* Use the `-AzContext` parameter with any Azure PowerShell cmdlets to provide an Azure context object:

  ```azurepowershell-interactive
  $context = Get-AzContext -Name 'mycontext' # Get an Azure context object
  $creds = Get-Credential
  $job = Start-Job { param($context, $vmadmin) New-AzVM -Name MyVm -AzContext $context -Credential $vmadmin} -ArgumentList $context,$creds }
  ```

  If context persistence is disabled, the `-AzContext` argument is required.

* Use the `-AsJob` switch provided by some Azure PowerShell cmdlets. This switch automatically starts
  the cmdlet as a PowerShell Job, using the currently active Azure context:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $job = New-AzVM -Name MyVm -Credential $creds -AsJob
  ```

  To see if a cmdlet supports `-AsJob`, check its reference documentation. The `-AsJob` switch doesn't require
  context autosave to be enabled.

You can check the status of a running job with the [Get-Job](/powershell/module/microsoft.powershell.core/get-job) 
cmdlet. To get the output from a job so far, use the [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job) cmdlet.

To check an operation's progress remotely on Azure, use the `Get-` cmdlets associated with the type of resource being
modified by the job:

```azurepowershell-interactive
$creds = Get-Credential
$context = Get-AzContext -Name 'mycontext'
$vmName = "MyVm"

$job = Start-Job { param($context, $vmName, $vmadmin) New-AzVM -Name $vmName -AzContext $context -Credential $vmadmin} -ArgumentList $context,$vmName,$creds }

Get-Job $job
Get-AzVM -Name $vmName
```

## See Also

* [Azure PowerShell contexts](context-persistence.md)
* [About PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)
* [Get-Job reference](/powershell/module/microsoft.powershell.core/get-job)
* [Receive-Job reference](/powershell/module/microsoft.powershell.core/receive-job)
