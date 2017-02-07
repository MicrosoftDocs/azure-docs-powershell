---
ms.assetid: DB6554D7-8649-4E9F-9525-88F28D2A8C69
ms.title: Azure PowerShell WebPI Installer | Microsoft Docs
ms.prod: azure
ms.service: powershell
author: twitchax
ms.author: aaroney
ms.manager: carmonm
---

# Azure PowerShell WebPI Installer

Installing the latest Azure PowerShell from WebPI is the same as it was for previous versions.
Download [Azure PowerShell](http://aka.ms/webpi-azps) and start the install. If you have Azure
PowerShell 0.9.x installed, it is uninstalled as part of the upgrade. If you installed Azure
PowerShell modules from PowerShell Gallery, the installer automatically removes the modules
before installation to ensure a consistent Azure PowerShell environment.

> [!NOTE]
> If you have previously installed Azure modules from the PowerShell Gallery, the
> installer will automatically remove them. This prevents confusion about which module versions you
> have installed and where they are located. PowerShell Gallery modules will normally install in
> `$env:ProgramFiles\WindowsPowerShell\Modules`. In contrast, the WebPI installer will install the
> Azure modules in `$env:ProgramFiles(x86)\Microsoft SDKs\Azure\PowerShell\`. If an error occurs
> during install, you can manually remove the Azure* folders in your
> `$env:ProgramFiles\WindowsPowerShell\Modules` folder, and try the installation again.

Once the installation completes, your `$env:PSModulePath` setting should include the directories
containing the Azure PowerShell cmdlets.

```powershell
# To make sure the Azure PowerShell module is available after you install
Get-Module -ListAvailable Azure*
```

> [!NOTE]
> There is a known issue with PowerShell `$env:PSModulePath` that can occur when
> installing from WebPI. If your computer requires a restart due to system updates or other
> installations, it may cause updates `$env:PSModulePath` to not include the path where Azure
> PowerShell is installed. If this occurs, you may see a 'cmdlet not recognized' message when
> attempting to use Azure PowerShell cmdlets after the installation or upgrade. If this occurs,
> restarting the machine should fix the problem.

If you receive a message like the following when attempting to load or execute cmdlets:

```
PS C:\> Get-AzureRmResource
Get-AzureRmResource : The term 'Get-AzureRmResource' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:1
+ Get-AzureRmResource
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Get-AzureRmResource:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

This can be corrected by restarting the machine or importing the cmdlets from C:\Program
Files\WindowsPowerShell\Modules\Azure\XXXX\ as following (where XXXX is the version of PowerShell
installed:

```powershell
Import-Module "C:\Program Files\WindowsPowerShell\Modules\Azure\XXXX\azure.psd1"
Import-Module "C:\Program Files\WindowsPowerShell\Modules\Azure\XXXX\expressroute\expressroute.psd1"
```