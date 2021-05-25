---
title: Uninstall Azure PowerShell
description: How to perform a complete uninstall of Azure PowerShell
ms.date: 09/15/2020
ms.devlang: powershell
ms.topic: conceptual 
ms.custom: devx-track-azurepowershell 
ms.service: azure-powershell
---
# How to uninstall Azure PowerShell modules

This article tells you how to uninstall an older version of Azure PowerShell, or completely remove
it from your system. If you've decided to completely uninstall Azure PowerShell, give us some
feedback through the [Send-Feedback](/powershell/module/az.accounts/send-feedback) cmdlet. If you
encountered a bug, we'd appreciate it if you
[file a GitHub issue](https://github.com/azure/azure-powershell/issues) so that it can be fixed.

## Uninstall the Az module

If you have the Az module installed on your system and would like to uninstall it, there are
two options. Which method you follow depends on how you installed the Az module. If you're not
sure of your original installation method, follow the MSI steps for uninstalling first.

### Option 1: Uninstall the Az PowerShell module from MSI

If you installed Az PowerShell module using the MSI package, you must uninstall through the Windows
system rather than PowerShell.

|         Platform         |                      Instructions                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Start > Settings > Apps                                |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen, you should see **Azure PowerShell** in the program listing. This is the app to
uninstall. If you don't see this program listed, then you installed through PowerShellGet, and
should follow the next set of instructions.

### Option 2: Uninstall the Az PowerShell module from PowerShellGet

To uninstall the Az modules, you can use the
[Uninstall-Module](/powershell/module/powershellget/uninstall-module) cmdlet. However,
`Uninstall-Module` only uninstalls one module. To remove the Az PowerShell module completely, you
must uninstall each module individually. Uninstallation can be complicated if you have more than one
version of Azure PowerShell installed.

To check which versions of the Az PowerShell module you've installed, run the following command:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions
```

```output
Version             Name                           Repository           Description
-------             ----                           ----------           -----------
3.8.0               Az                             PSGallery            Microsoft Azure PowerShell
4.1.0               Az                             PSGallery            Microsoft Azure PowerShell
```

The following script queries the PowerShell Gallery to get a list of dependent submodules. Then,
the script uninstalls the correct version of each submodule. You need to have administrator access
to run this script in a scope other than **Process** or **Current User**.

```powershell-interactive
function Uninstall-AzModule {
  [CmdletBinding(SupportsShouldProcess)]
  param(
    [ValidateNotNullOrEmpty()]
    [ValidateSet('Az','AzureRM','Azure')]
    [string]$Name = 'Az',

    [Parameter(Mandatory)]
    [string]$Version,

    [switch]$AllowPrerelease
  )

  $Params = @{}

  if ($PSBoundParameters.AllowPrerelease) {
    $Params.AllowPrerelease = $true
  }

  $IsAdmin = ([Security.Principal.WindowsPrincipal] [Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([Security.Principal.WindowsBuiltInRole] 'Administrator')

  if (-not(Get-InstalledModule -Name $Name -RequiredVersion $Version -ErrorAction SilentlyContinue -OutVariable RootModule @Params)) {

    Write-Warning -Message "Uninstall aborted. $Name version $Version not found."

  } elseif (($RootModule.InstalledLocation -notlike "*$env:USERPROFILE*") -and ($IsAdmin -eq $false)) {

    Write-Warning -Message "Uninstall aborted. $Name version $Version exists in a system path. PowerShell must be run elevated as an admin to remove it."

  } elseif ((Get-Process -Name powershell, pwsh -OutVariable Sessions -ErrorAction SilentlyContinue).Count -gt 1) {

    Write-Warning -Message "Uninstall aborted. Please close all other PowerShell sessions before continuing. There are currently $($Sessions.Count) PowerShell sessions running."

  } else {
    Write-Verbose -Message 'Creating list of dependencies...'
    $target = Find-Module -Name $Name -RequiredVersion $Version @Params

    $AllModules = @([pscustomobject]@{
      Name = $Name
      Version = $Version
    })

    $AllModules += foreach ($dependency in $target.Dependencies) {
      switch ($dependency.keys) {
        {$_ -contains 'RequiredVersion'} {$UninstallVersion = $dependency.RequiredVersion; break}
        {$_ -contains 'MinimumVersion'} {$UninstallVersion = $dependency.MinimumVersion; break}
      }

      [pscustomobject]@{
        Name = $dependency.Name
        Version = $UninstallVersion
      }
    }

    [int]$i = 100 / $AllModules.Count

    foreach ($module in $AllModules) {
      Write-Progress -Activity 'Uninstallation in Progress' -Status "$i% Complete:" -PercentComplete $i
      $i++

      if (Get-InstalledModule -Name $module.Name -RequiredVersion $module.Version -ErrorAction SilentlyContinue @Params) {
        Write-Verbose -Message "Uninstalling $($module.Name) version $($module.Version)"

        Remove-Module -FullyQualifiedName @{ModuleName=$module.Name;ModuleVersion=$module.Version} -ErrorAction SilentlyContinue

        try {
          if ($PSCmdlet.ShouldProcess("$($module.Name) version $($module.Version)")) {
            Uninstall-Module -Name $module.Name -RequiredVersion $module.Version -Force -ErrorAction Stop @Params
          }
          $State = 'Uninstalled'
        } Catch {
          $State = 'Manual uninstall required'
          Write-Verbose -Message "$($module.Name) version: $($module.Version) may require manual uninstallation."
        }

      } else {
        $State = 'Not found'
        Write-Verbose -Message "$($module.Name) version: $($module.Version) not found."
      }

      if (-not $PSBoundParameters.WhatIf) {
        [pscustomobject]@{
          ModuleName = $module.Name
          Version = $module.Version
          State = $State
        }
      }

    }
  }
}
```

To use this function, copy and paste the code into your PowerShell session. The following example
shows how to run the function to remove an older version of the Az PowerShell module and its
submodules.

```powershell-interactive
Uninstall-AzModule -Name Az -Version 1.8.0
```

As the script runs, it displays the **Name**, **Version**, and **State** of each submodule that is
being uninstalled. To run the script to only see what would be deleted, without removing it, specify
the `-WhatIf` parameter.

```output
ModuleName              Version  State
----------              -------  -----
Az.Accounts             1.5.1    Not found
Az.Aks                  1.0.1    Uninstalled
Az.AnalysisServices     1.1.0    Uninstalled
Az.ApiManagement        1.0.0    Uninstalled
Az.ApplicationInsights  1.0.0    Uninstalled
...
```

> [!IMPORTANT]
> If this script can't match an exact dependency with the same version to uninstall, it won't
> uninstall _any_ version of that dependency. This is because there may be other versions of the
> target module on your system which rely on these dependencies.

Run the following example for every version of the Az PowerShell module that you want to uninstall.
For convenience, the following script uninstalls all versions of Az **except** for the latest.

```powershell-interactive
$Modules = Get-InstalledModule -Name Az -AllVersions |
    Sort-Object -Property Version -Descending |
        Select-Object -Skip 1
$Modules | ForEach-Object {Uninstall-AzModule -Name $_.Name -Version $_.Version}
```

## Uninstall the AzureRM module

If you have the Az module installed on your system and would like to uninstall AzureRM, there are
two options. Which method you follow depends on how you installed the AzureRM module. If you're not
sure of your original installation method, follow the MSI steps for uninstalling first.

### Option 1: Uninstall the AzureRM PowerShell module from MSI

If you installed the AzureRM PowerShell module using the MSI package, you must uninstall through the
Windows system rather than PowerShell.

|         Platform         |                      Instructions                      |
| ------------------------ | ------------------------------------------------------ |
| Windows 10               | Start > Settings > Apps                                |
| Windows 7 </br>Windows 8 | Start > Control Panel > Programs > Uninstall a program |

Once on this screen, you should see **Azure PowerShell** or **Microsoft Azure PowerShell - Month
Year** in the program listing. This is the app to uninstall. If you don't see this program listed,
then you installed through PowerShellGet, and should follow the next set of instructions.

### Option 2: Uninstall the AzureRM PowerShell module from PowerShellGet

If you installed AzureRM with PowerShellGet, then you can remove the modules with the
[Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm) cmdlet, available as part of
the `Az.Accounts` module.

In order to use the `Az.Accounts` module, you will need to have the Az module installed.  Having both the AzureRM and the Az modules installed at the same time is not supported however the Az module can be used to immediately uninstall the AzureRM module.  You can install the Az module and bypass the AzureRM module warning with the following command if you do not have the Az module installed already:

```powershell-interactive
Install-Module -Name Az -AllowClobber -Scope CurrentUser
```

Once the Az module is installed, the following command removes _all_ AzureRM modules from your machine. It
requires administrator privileges.

```powershell-interactive
Uninstall-AzureRm
```
