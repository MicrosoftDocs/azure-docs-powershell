# Azure Service Management Cmdlets

The Azure Service Management reference provides information about Microsoft Azure PowerShell modules that help you to automate your Azure service management tasks.
This reference includes information about the Azure PowerShell modules, including system requirements, download links, and configurations tasks.
It also includes cmdlet help for the cmdlets and functions in the Azure PowerShell modules.

There are no breaking changes for the Service Management cmdlets between Azure PowerShell 2.0 and Azure PowerShell 3.0.

## To install the cmdlets

To install the cmdlets by using PowerShell Gallery using **PowerShellGet**, you must have Windows Management Framework (WMF) 5.0.
For more information, see [Windows Management Framework 5.0 Production Preview](https://www.microsoft.com/en-us/download/details.aspx?id=48729).
By default, WMF 5.0 comes installed on Windows 10.
Run the following command from the Windows PowerShell console running as Administrator:

```PowerShell
PS C:\> Install-Module Azure
```

This command installs the Azure PowerShell 3.0 Service Management module from PowerShell Gallery.
After you install this module, you can import the module by running the following command:

```PowerShell
PS C:\> Import-Module Azure
```

## To use the cmdlets
To start working with the Azure Service Management cmdlets, first log on to your Azure account.
To log on to your account, run the following command:

```PowerShell  
PS C:\> Add-AzureAccount
```

After logging into Azure, Azure PowerShell creates a context for the given session.
That context contains the Azure PowerShell environment, account, tenant, and subscription that will be used for all cmdlets within that session.
Now you are ready to use the modules below.

## Azure Service Management cmdlets

Azure PowerShell modules are not included in Windows.
Before you can use the cmdlets in the modules, you need to download the modules you want to use and set up your environment so you can connect to Azure from Azure PowerShell.
For instructions, see the page for each module.

Azure PowerShell modules are updated frequently.
If you notice that the online cmdlet help includes cmdlets or parameters that are not in your module, download and install the latest version of the module.
To find the version of your module, type: `(Get-Module <ModuleName>).Version`.

For sample scripts that can help you automate some of the common tasks in Azure, see the [Windows Azure Script Center](http://www.windowsazure.com/documentation/scripts/).

For general information about installing, learning, using, and customizing Windows PowerShell, see [Scripting with Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=320210).
