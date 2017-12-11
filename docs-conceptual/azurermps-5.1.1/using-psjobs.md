---
title: Running cmdlets in parallel using PowerShell jobs
description: How to run cmdlets in parallel using the -AsJob parameter.
services: azure
author: sdwheeler
ms.author: sewhee
manager: carmonm
ms.product: azure
ms.service: azure-powershell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 12/11/2017
---

# Running cmdlets in parallel using PowerShell jobs

PowerShell supports asynchronous action with [PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).
Azure PowerShell is heavily dependent on making, and waiting for, network calls to Azure. As a
developer, you may often find yourself looking to make multiple non-blocking calls to Azure in a
script, or you may find that you want to create Azure resources in the REPL without blocking the
current session. To address these needs, Azure PowerShell provides first-class
[PSJob](/powershell/module/microsoft.powershell.core/about/about_jobs) support.

## Context Persistence and PSJobs

PSJobs are run in separate processes, which means that information about your Azure connection must
be properly shared with the jobs you create. Upon connecting your Azure account to your PowerShell
session with `Connect-AzureRmAccount`, you can pass the context to a job.

```powershell
$job = Start-Job { param($context) New-AzureRmVM -Name MyVm -AzureRmContext $context } -Arguments (Get-AzureRmContext)
```

However, if you have chosen to have your context automatically saved with
`Enable-AzureRmContextAutosave`, the context is automatically shared with any jobs you create.

```powershell
Enable-AzureRmContextAutosave
$job = Start-Job { New-AzureRmVM -Name MyVm }
```

## Automatic Jobs with `-AsJob`

As a convenience, Azure PowerShell also provides an `-AsJob` switch on some long-running cmdlets.
The `-AsJob` switch makes creating PSJobs even easier.

```powershell
$job = New-AzureRmVM -Name MyVm -AsJob
```

You can inspect the job at any time with `Get-Job`.

```powershell
Get-Job $job
```

```Output
PS C:\temp> get-job

Id  Name   PSJobTypeName   State     HasMoreData   Location     Command
--  ----   -------------   -----     -----------   --------     -------
1   Job1   BackgroundJob   Blocked   True          localhost    New-AzureRmVM -Name M...
```

Subsequently, upon completion, you can obtain the result of the job with `Receive-Job`.

> [!NOTE]
> `Receive-Job` returns the result from the cmdlet as if the `-AsJob` flag were not present.
> For example, the `Receive-Job` result of `Do-Action -AsJob` is of the same type as the result of
> `Do-Action`.

```powershell
$vm = Receive-Job $job
```

## Example Scenarios

Create multiple VMs at once.

```powershell
!!!CHECK!!!
# Create 10 jobs.
for($k = 0; $k -lt 10; $k++) {
    New-AzureRmVm -Name MyVm$k -AsJob
}

# Get all jobs and wait on them.
Get-Job | Wait-Job
```