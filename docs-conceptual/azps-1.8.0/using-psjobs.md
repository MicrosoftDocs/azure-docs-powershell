---
title: Run Azure PowerShell cmdlets in PowerShell Jobs
description: Learn how to run Azure PowerShell cmdlets in parallel or as background tasks, using -AzJob and Start-Job.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/07/2019
---

# Run Azure PowerShell cmdlets in PowerShell Jobs

PowerShell supports asynchronous tasks through PowerShell Jobs, with credentials provided by Azure Context objects.
Azure PowerShell depends on connecting to the cloud and waiting for responses, so running Azure PowerShell cmdlets
blocks your PowerShell session. Powershell Jobs allow you to run cmdlets in the background or do multiple tasks at once,
from inside a single terminal.

This article is a brief overview of how to run Azure PowerShell cmdlets in PowerShell Jobs and check for completion. Running commands
in Azure PowerShell requires the use of credential contexts, which are covered in detail in
[Credential contexts in Azure PowerShell](context-persistence.md). To learn more about PowerShell Jobs, see
[About PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

## Azure contexts with PowerShell jobs

Since PowerShell Jobs are run as separate processes, your Azure credentials must be shared with them. Credentials are passed
as Azure contexts:

* Automatic context persistence, which is enabled by default and preserves your sign-in information across multiple sessions.
  With context persistence enabled, the current context is passed to the new process started by `Start-Job`:

  ```azurepowershell-interactive
  Enable-AzContextAutosave # Enables context autosave if not already on
  $creds = Get-Credential
  $job = Start-Job { param($vmadmin) New-AzVM -Name MyVm -Credential $vmadmin } -ArgumentList $creds
  ```

* Provide the `-AzContext` parameter. Using this argument runs the job against the provided context:

  ```azurepowershell-interactive
  $context = Get-AzContext -Name 'mycontext' # Get Azure context object
  $creds = Get-Credential
  $job = Start-Job { param($context, $vmadmin) New-AzVM -Name MyVm -AzContext $context -Credential $vmadmin} -ArgumentList $context,$creds }
  ```

  If context persistence is disabled, the `-AzContext` argument is required.

* Some cmdlets that start long-running operations offer the `-AsJob` switch to
  automatically start the cmdlet in a PowerShell Job:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $job = New-AzVM -Name MyVm -Credential $creds -AsJob
  ```

  This switch works whether or not context persistence is enabled.

You can check the status of a running job with the [Get-Job](/powershell/module/microsoft.powershell.core/get-job) cmdlet. To
get the output from a job so far, use the [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job) cmdlet.

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
