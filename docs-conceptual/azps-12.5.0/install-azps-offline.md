---
description: Learn how to install Azure PowerShell offline on a system without access to the internet or the PowerShell Gallery.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
title: Offline Installation of Azure PowerShell
---

# Offline Installation of Azure PowerShell

In some environments, it's not possible to connect to the internet or the PowerShell Gallery. In
those situations, you can install the Az PowerShell module offline using one of these methods.

> [!NOTE]
> The options for offline installation in this article require at least one system with internet
> access to download the **Az** PowerShell module, which can be different from the system where you
> plan to install the module.

## Prerequisites

- Install a supported version of [PowerShell version 7 or higher][install-powershell]
- Windows PowerShell 5.1 is also supported if your're running a Windows operating system.

## Cross platform

The following installation options for the Az PowerShell module are available cross-platform on all
platforms including Windows, Linux, and macOS.

### Install from tar archive

> [!TIP]
> The `tar` command-line utility is required to use this installation option. Its available by
> default on Windows 10 version 1803 or higher, most Linux distributions, and current versions of
> macOS.

1. On a system with access to the internet, define the destination path where you want to save the
   tar archive.

   ```powershell
   $downloadFolderPath = "$home/Downloads"
   ```

1. Verify the download folder exists. Create the folder otherwise.

   ```powershell
   if (-not (Test-Path -Path $downloadFolderPath -PathType Container)) {
       New-Item -Path $downloadFolderPath -ItemType Directory
   }
   ```

1. Determine the URL of the tar archive for the latest Az PowerShell module version on GitHub.

   ```powershell
   $tarSourceUrl = (
       Invoke-RestMethod -Uri https://api.github.com/repos/azure/azure-powershell/releases/latest |
       Select-Object -ExpandProperty assets | Where-Object name -like Az-Cmdlets-*.tar.gz
   ).browser_download_url
   ```

1. Store the tar filename and destination filepath in variables.

   ```powershell
   $fileName = Split-Path -Path $tarSourceUrl -Leaf
   $downloadFilePath = Join-Path -Path $downloadFolderPath -ChildPath $fileName
   ```

1. Download the tar archive from GitHub using PowerShell.

   ```powershell
   Invoke-WebRequest -Uri $tarSourceUrl -OutFile $downloadFilePath
   ```

1. Unblock the downloaded file if you're running a Windows operating system.

   ```powershell
   if ($PSVersionTable.PSVersion.Major -le 5 -or $IsWindows -eq $true) {
       Unblock-File -Path $downloadFilePath
   }
   ```

   > [!NOTE]
   > Copy the tar archive to your offline system. Define the `$downloadFilePath` and
   > `$downloadFolderPath` variables or specify actual values instead of using the variables in the
   > following commands on your offline system.

1. Extract the contents of the tar archive.

   ```powershell
   tar zxf $downloadFilePath -C $downloadFolderPath
   ```

1. Run the `InstallModule.ps1` script that's one of the extracted files on the offline system where
   you want to install the Az PowerShell module.

   ```powershell
   .$downloadFolderPath/InstallModule.ps1
   ```

### Save and copy installation

Download the Az PowerShell module with `Save-Module` or `Save-PSResource` to a network location
using a system with access to the internet and the PowerShell Gallery. These commands save the Az
module and its dependencies to the specified location. Use the saved modules as the installation
source and copy them to the offline system.

### Install from a private repository

Create a private repository on your local network and use it as installation source for your offline
system. To learn more, see [Working with Private PowerShellGet Repositories][private-repositories].

This method allows you to cache PowerShell modules on a single server or file share to be deployed
with **PowerShellGet** or **Microsoft.PowerShell.PSResourceGet** to any disconnected systems.

## Windows

On Windows, you also have the option of installing the Az PowerShell module with an MSI if you're
using Windows PowerShell version 5.1.

> [!IMPORTANT]
> Keep in mind that the MSI installer only works for Windows PowerShell 5.1.

- [Install Azure PowerShell on Windows with the MSI Installer][install-azps-msi].

## Troubleshooting

For solutions to common installation issues with the Az PowerShell module, see
[Troubleshoot installation problems with the Az PowerShell module][troubleshoot-install].

## See also

- [Save-Module][save-module]
- [Save-PSResource][save-psresource]

## Next Steps

To learn more about managing your Azure resources with the Az PowerShell module, see
[Get Started with Azure PowerShell][get-started-azps].

<!-- link references -->

[install-powershell]: /powershell/scripting/install/installing-powershell-on-macos
[private-repositories]: /powershell/scripting/gallery/how-to/working-with-local-psrepositories
[install-azps-msi]: /powershell/azure/install-azps-windows?tabs=powershell&pivots=windows-msi
[troubleshoot-install]: troubleshooting.md#installation
[save-module]: /powershell/module/PowershellGet/Save-Module
[save-psresource]: /powershell/module/microsoft.powershell.psresourceget/save-psresource
[get-started-azps]: get-started-azureps.md
