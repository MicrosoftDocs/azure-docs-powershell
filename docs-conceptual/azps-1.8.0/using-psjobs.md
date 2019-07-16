---
title: Run Azure PowerShell cmdlets in PowerShell Jobs
description: Learn how to run Azure PowerShell cmdlets in parallel or as background tasks, using -AzJob and Start-Job.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 07/15/2019
---

# Run Azure PowerShell cmdlets in PowerShell Jobs

PowerShell supports asynchronous tasks through PowerShell Jobs. Azure PowerShell depends on connecting to the
Azure cloud and waiting for responses, so running Azure PowerShell cmdlets in your main PowerShell session blocks it.
Jobs allow you to run cmdlets in the background or easily do multiple Azure tasks at once.

This article is an overview of what you need to pass to PowerShell Jobs to have Azure PowerShell cmdlets work
correctly and how to check for job completion. To learn more about PowerShell Jobs, see
[About PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).

## Context Persistence and PowerShell Jobs

Since PowerShell Jobs are run as separate processes, your Azure credentials must be shared with them. You can pass credentials to a job with:

* Automatic context persistence, which is enabled by default and preserves your sign in information across multiple sessions.
  The current context is passed to the new process started by `Start-Job`:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $job = Start-Job { param($vmadmin) New-AzVM -Name MyVm -Credential $vmadmin } -ArgumentList $creds
  ```

* [Azure contexts](context-persistence.md), which can be explicitly passed to a command with the `-AzContext` parameter.
  Using this argument runs the job against that context, instead of the currently active one.

  ```azurepowershell-interactive
  $creds = Get-Credential
  $context = Get-AzContext -Name 'mycontext'
  $job = Start-Job { param($context, $vmadmin) New-AzVM -Name MyVm -AzContext $context -Credential $vmadmin} -ArgumentList $context,$creds }
  ```

  If context persistence is disabled, the `-AzContext` argument is required.

You can check the status of a running job with the [Get-Job](/powershell/module/microsoft.powershell.core/get-job) cmdlet. To
get the result of a job, use the [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job) cmdlet. `Receive-Job`
returns the result of the command that was run in the job, if it's completed.

> [!IMPORTANT]
> To check the state of a running job on the cloud, use `Get-Job` to see the job status and any
> `Get-` cmdlets associated with the type of resource being modified to check its current status.

## Starting PowerShell jobs with `-AsJob`

As a convenience, Azure PowerShell also provides an `-AsJob` switch on some long-running cmdlets. This switch automatically creates a job and returns a job object, rather than the standard cmdlet repsonse.

```azurepowershell-interactive
$creds = Get-Credential
$job = New-AzVM -Name MyVm -Credential $creds -AsJob
Receive-Job $job
```
