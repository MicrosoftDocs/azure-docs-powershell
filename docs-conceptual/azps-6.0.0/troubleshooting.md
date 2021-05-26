---
title: Troubleshooting the Azure Az PowerShell module
description: Troubleshooting the Azure Az PowerShell module.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 04/7/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Troubleshooting the Azure Az PowerShell module

## Enable debug logging

One of the first steps you should take in troubleshooting a problem with the Azure Az PowerShell module is to enable
debug logging.

To enable debug logging on a per command basis, specify the **Debug** parameter.

```azurepowershell-interactive
Get-AzResource -Name 'DoesNotExist' -Debug
```

To enable debug logging for an entire PowerShell session, you set the value of the
**DebugPreference** variable to `Continue`.

```azurepowershell-interactive
$DebugPreference = 'Continue'
```

## Command found but could not be loaded

The following message is returned by PowerShell when you attempt to run any of the Az PowerShell commands.

```Output
Connect-AzAccount: The 'Connect-AzAccount' command was found in the module 'Az.Accounts', but the module could not be loaded. For more information, run 'Import-Module Az.Accounts'.
```

This message occurs when you have both the Az and AzureRM PowerShell modules installed on the same
Windows-based system and they exist in the
[$env:PSModulePath](/powershell/module/microsoft.powershell.core/about/about_psmodulepath) for the
same version of PowerShell.

> [!IMPORTANT]
> When AzureRM is installed in the `AllUsers` scope of Windows PowerShell, it's installed in a
> location that's part of the `$env:PSModulePath` for PowerShell 7. This is not supported due to
> conflicts between the AzureRM and Az PowerShell modules.

Both Az and AzureRM may coexist on the same Windows system, but only if AzureRM is installed in the
`CurrentUser` scope of Windows PowerShell and Az installed in PowerShell 7. For more information, see
[Install the Azure Az PowerShell module](/powershell/azure/install-az-ps).
