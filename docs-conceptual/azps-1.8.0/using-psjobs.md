---
title: Run Azure PowerShell cmdlets in PowerShell Jobs
description: Learn how to run Azure PowerShell cmdlets in parallel or as background tasks, using -AzJob and Start-Job.
author: sptramer
ms.author: sttramer
manager: carmonm
ms.devlang: powershell
ms.topic: conceptual
ms.date: 06/25/19
---

# Run Azure PowerShell cmdlets in PowerShell Jobs

PowerShell supports asynchronous tasks through [PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).
Azure PowerShell is heavily dependent on making network calls to the Azure cloud, and then waiting for responses from the service.
In many situations, non-blocking behavior is preferable so that you can continue to do work in a PowerShell session while waiting
for an Azure operation to complete. To help with running Azure PowerShell commands in a non-blocking fashion, all Azure PowerShell
cmdlets offer first-class support for jobs.

## Context Persistence and PowerShell Jobs

Since PowerShell Jobs are run as separate processes, your Azure credentials must be shared with them. This is done through one of two mechanisms:

* Automatic context persistence, which is enabled by default and preserves your sign in information across multiple sessions:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $job = Start-Job { param($vmadmin) New-AzVM -Name MyVm -Credential $vmadmin} -ArgumentList $creds }
  ```

* [Azure contexts](context-persistence.md), which can be explicitly passed to a command with the `-DefaultProfile` or `-AzContext` parameter. This
  allows you to use a context _other_ than the currently active context when running a command as a job:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $context = Get-AzContext -Name 'mycontext'
  $job = Start-Job { param($context, $vmadmin) New-AzVM -Name MyVm -AzContext $context -Credential $vmadmin} -ArgumentList $context,$creds }
  ```

You can check the status of a running job with the [Get-Job](/powershell/module/microsoft.powershell.core/get-job) cmdlet. To
get the result of a job, use the [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job) cmdlet. `Receive-Job`
returns the result of the command that was run in the job.

> [!IMPORTANT]
> If the operation that you started for the job hasn't gotten a response from the Azure cloud yet, `Recieve-Job` will block
> until it has a result to pass back. For this reason it's recommended to use `Get-Job` and any `Get-` cmdlets associated with
> the type of resource being modified to check its current status.

## Starting PowerShell jobs with `-AsJob`

As a convenience, Azure PowerShell also provides an `-AsJob` switch on some long-running cmdlets. This switch automatically
creates a job, and returns the job object so that you can wait on it or check results.

```azurepowershell-interactive
$creds = Get-Credential
$job = New-AzVM -Name MyVm -Credential $creds -AsJob
```
