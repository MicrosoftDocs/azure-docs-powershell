---
title: Install Azure PowerShell with PowerShellGet
description: How to install Azure PowerShell with PowerShellGet
ms.devlang: powershell
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Install Azure PowerShell

This article explains how to install the Azure PowerShell modules using [PowerShellGet][01]. These
instructions work on Windows, Linux, and macOS platforms.

Azure PowerShell is also available in Azure [Cloud Shell][02].

## Requirements

Azure PowerShell works with PowerShell 5.1 or higher on Windows, or PowerShell Core 6.x and later on
all platforms. You should install the [latest version of PowerShell][03] available for your
operating system. Azure PowerShell has no additional requirements when run on PowerShell 6.2.4 and
later.

To check your PowerShell version, run the command:

```azurepowershell-interactive
$PSVersionTable.PSVersion
```

To use Azure PowerShell in PowerShell 5.1 on Windows:

1. Update to [Windows PowerShell 5.1][04]. If you're on Windows 10 version 1607 or higher, you
   already have PowerShell 5.1 installed.
2. Install [.NET Framework 4.7.2 or later][05].
3. Make sure you have the latest version of PowerShellGet. Run
   `Install-Module -Name PowerShellGet -Force`.

## Install the Azure PowerShell module

> [!WARNING]
> We do not support having both the AzureRM and Az modules installed for PowerShell 5.1 on Windows
> at the same time. If you need to keep AzureRM available on your system, install the Az module for
> PowerShell 6.2.4 or later.

Using the PowerShellGet cmdlets is the preferred installation method. Install the Az module for the
current user only. This is the recommended installation scope. This method works the same on
Windows, Linux, and macOS platforms. Run the following command from a PowerShell session:

```powershell-interactive
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Scope CurrentUser
}
```

By default, the PowerShell gallery isn't configured as a trusted repository for PowerShellGet. The
first time you use the PSGallery you see the following prompt:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Answer `Yes` or `Yes to All` to continue with the installation.

Installing the module for all users on a system requires elevated privileges. Start the PowerShell
session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:

```powershell-interactive
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Scope AllUsers
}
```

The Az module is a rollup module for the Azure PowerShell cmdlets. Installing it downloads all of
the generally available Az PowerShell modules, and makes their cmdlets available for use.

## Install offline

In some environments, it's not possible to connect to the PowerShell Gallery. In those situations,
you can still install offline using one of these methods:

* Download the modules to another location in your network and use that as an installation source.
  This method allows you to cache PowerShell modules on a single server or file share to be deployed
  with PowerShellGet to any disconnected systems. Learn how to set up a local repository and install
  on disconnected systems with [Working with local PowerShellGet repositories][06].
* [Download the Azure PowerShell MSI][07] to a machine connected to the network, and then copy the
  installer to systems without access to PowerShell Gallery. Keep in mind that the MSI installer
  only works for PowerShell 5.1 on Windows.
* Save the module with [Save-Module][08] to a file share, or save it to another source and manually
  copy it to other machines:

  ```powershell-interactive
  Save-Module -Name Az -Path '\\server\share\PowerShell\modules' -Force
  ```

## Troubleshooting

Here are some common problems seen when installing the Azure PowerShell module. If you experience a
problem not listed here, [file an issue on GitHub][09].

### Proxy blocks connection

If you get errors from `Install-Module` that indicate the PowerShell Gallery is unreachable, you may
be behind a proxy. Different operating systems and network environment have different requirements
for configuring a system-wide proxy. Contact your system administrator for your proxy settings and
how to configure them for your environment.

PowerShell itself may not be configured to use this proxy automatically. With PowerShell 5.1 and
later, configure the PowerShell session to use a proxy using the following commands:

```powershell
$webClient = New-Object System.Net.WebClient
$webClient.Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials
```

If your operating system credentials are configured correctly, this configuration routes PowerShell
requests through the proxy. To have this setting persist between sessions, add the commands to your
[PowerShell profile][10].

To install the package, your proxy needs to allow HTTPS connections to the following address:

* `https://www.powershellgallery.com`

## Sign in

To start working with Azure PowerShell, sign in with your Azure credentials.

```azurepowershell-interactive
# Connect to Azure with a browser sign in token
Connect-AzAccount
```

> [!NOTE]
> If you've disabled module autoloading, manually import the module with `Import-Module -Name Az`.
> Because of the way the module is structured, this can take a few seconds.

You'll need to repeat these steps for every new PowerShell session you start. To learn how to
persist your Azure sign in across PowerShell sessions, see
[Persist user credentials across PowerShell sessions][11].

## Update the Azure PowerShell module

To update any PowerShell module, you should use the same method used to install the module. For
example, if you originally used `Install-Module`, then you should use [Update-Module][12] to get the
latest version. If you originally used the MSI package then you should download and install the new
MSI package.

The PowerShellGet cmdlets cannot update modules that were installed from an MSI package. MSI
packages do not update modules that were installed using PowerShellGet. If you have any issues
updating using PowershellGet, then you should **reinstall**, rather than **update**. Reinstalling is
done the same way as installing, but you need to add the `-Force` parameter:

```powershell
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Force
}
```

Unlike MSI-based installations, installing or updating using PowerShellGet does not remove older
versions that may exist on your system. To remove old versions of Azure PowerShell from your system,
see [Uninstall the Azure PowerShell module][13]. For more information about MSI-based installations,
see [Install Azure PowerShell with an MSI][14].

## Use multiple versions of Azure PowerShell

It's possible to install more than one version of Azure PowerShell. To check if you have multiple
versions of Azure PowerShell installed, use the following command:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions | Select-Object -Property Name, Version
```

To remove a version of Azure PowerShell, see [Uninstall the Azure PowerShell module][13].

If you have more than one version of the module installed, module autoload and `Import-Module` load
the latest version by default.

You can install or load a specific version of the `Az` module by using the `-RequiredVersion`
parameter:

```powershell-interactive
# Install Az version 3.6.1
Install-Module -Name Az -RequiredVersion 3.6.1
# Load Az version 3.6.1
Import-Module -Name Az -RequiredVersion 3.6.1
```

## Provide feedback

If you find a bug in Azure PowerShell, [file an issue on GitHub][09]. To provide feedback from the
command line, use the [Send-Feedback][17] cmdlet.

## Next Steps

To learn more about the Azure PowerShell modules and their features, see
[Get Started with Azure PowerShell][18]. If you're familiar with Azure PowerShell and need to
migrate from AzureRM, see [Migrate from AzureRM to Az][19].

<!-- link references -->
[01]: /powershell/gallery/powershellget/install-powershellget
[02]: /azure/cloud-shell/overview
[03]: /powershell/scripting/install/installing-powershell
[04]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[05]: /dotnet/framework/install
[06]: /powershell/gallery/how-to/working-with-local-psrepositories
[07]: install-az-ps-msi.md
[08]: /powershell/module/PowershellGet/Save-Module
[09]: https://github.com/azure/azure-powershell/issues
[10]: /powershell/module/microsoft.powershell.core/about/about_profiles
[11]: context-persistence.md
[12]: /powershell/module/powershellget/update-module
[13]: uninstall-az-ps.md
[14]: install-az-ps-msi.md
[17]: /powershell/module/az.accounts/send-feedback
[18]: get-started-azureps.md
[19]: migrate-from-azurerm-to-az.md
