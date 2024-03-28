---
title: Frequently Asked Questions (FAQ)
description: Frequently Asked Questions about Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual

ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Frequently asked questions about Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## What is Azure PowerShell?

Azure PowerShell is a set of cmdlets that allows you to manage Azure resources directly with
PowerShell. In December 2018, the Az PowerShell module became generally available. It's now the
recommended PowerShell module for interacting with Azure. To learn more about the Az PowerShell
module, see [Introducing the Az PowerShell module](/powershell/azure/new-azureps-module-az).

## How do I disable breaking change warning messages in Azure PowerShell?

To suppress the breaking change warning messages in Azure PowerShell, you'll need to set the
environment variable `SuppressAzurePowerShellBreakingChangeWarnings` to `true`.

```powershell
Set-Item -Path Env:\SuppressAzurePowerShellBreakingChangeWarnings -Value $true
```

## How do I disable the AzureRM retirement warning message in Azure PowerShell?

To suppress the AzureRM retirement warning message in Azure PowerShell, you'll need to set the
environment variable `SuppressAzureRmModulesRetiringWarning` to `true`.

```powershell
Set-Item -Path Env:\SuppressAzureRmModulesRetiringWarning -Value $true
```

One disadvantage of the previous example is you'll need to run the command for each new PowerShell
session unless you add it to your PowerShell profile.

To set the environment variable permanently, you can also use the following example.

```powershell
[System.Environment]::SetEnvironmentVariable('SuppressAzureRmModulesRetiringWarning', 'true', [System.EnvironmentVariableTarget]::User)
```
