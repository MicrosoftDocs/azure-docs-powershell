---
ms.assetid: DF332CD7-E3E5-4CC1-8C01-380B2065193C
ms.title: Get started with Azure PowerShell | Microsoft Docs
ms.prod: azure
ms.service: powershell
author: sdwheeler
ms.author: sewhee
ms.manager: carmonm
---

# Get started with Azure PowerShell cmdlets

Azure PowerShell is a set of modules that provide cmdlets to manage Azure with Windows PowerShell.
You can use the cmdlets to create, test, deploy, and manage solutions and services delivered through
the Azure platform. In most cases, the cmdlets can be used for the same tasks as the Azure Portal,
such as creating and configuring cloud services, virtual machines, virtual networks, and web apps.

## Step 1: Install Azure PowerShell

Azure PowerShell recommends installing from the PowerShell Gallery.  You need the PowerShellGet
module to use the [PowerShell Gallery](https://www.powershellgallery.com/). Alternatively, use the
Web Platform Installer (WebPI), or the MSI file available from
[GitHub](https://github.com/Azure/azure-powershell/releases/latest).

Install the latest Azure PowerShell from the PowerShell Gallery using an elevated Windows PowerShell
or PowerShell Integrated Scripting Environment (ISE) prompt:

```powershell
# Install the Azure Resource Manager modules from the PowerShell Gallery
Install-Module AzureRM
```

`Install-Module AzureRM` installs a rollup module for the Azure Resource Manager cmdlets. The
AzureRM module depends on a particular version range for each Azure Resource Manager module.
The included version range assures that no breaking module changes can be included when
installing AzureRM modules with the same major version. When you install the AzureRM module,
any Azure Resource Manager module that has not previously been installed will be downloaded
and installed from the PowerShell Gallery. For more information on the semantic versioning
used by Azure PowerShell modules, see [semver.org](http://semver.org).

For cmdlet information, check out the [Azure PowerShell Resource Manager](/powershell/resourcemanager/) reference.

## Step 2: Connect to an Azure account

You can run the cmdlets from the standard Windows PowerShell console, or from PowerShell Integrated
Scripting Environment (ISE). The cmdlets need your subscription information so they can manage your
services. You can purchase an Azure subscription if you don't already have one. For instructions,
see [How to buy Azure](http://go.microsoft.com/fwlink/p/?LinkId=320795).

1. Type `Login-AzureRmAccount`
2. Type the email address and password associated with your account. Azure authenticates and saves
   the credential information, and then closes the window.

--OR--

Sign into your work or school account:

```powershell
$cred = Get-Credential
Login-AzureRmAccount -Credential $cred
```

> [!NOTE]
> This non-interactive log in method only works with a work or school account. A work or
> school account is a user that is managed by your work or school, and defined in the Azure Active
> Directory instance for your work or school. If you do not currently have a work or school account,
> and are using a Microsoft account to log in to your Azure subscription, you can easily create one
> using the following steps.
>
> 1. Log in to the [Azure classic portal](https://manage.windowsazure.com), and click on
>    **Active Directory**.
> 2. If no directory exists, select **Create your directory** and provide the requested information.
> 3. Select your directory and add a new user. This new user can sign in using a work or school
>    account. During the creation of the user, you will be supplied with both an e-mail address for
>    the user and a temporary password. Save this information, as it is used in step 5 below.
> 4. From the Azure classic portal, select **Settings** and then select **Administrators**. Select
>    **Add**, and add the new user as a co-administrator. This allows the work or school account to
>    manage your Azure subscription.
> 5. Finally, log out of the Azure classic portal and then log back in using the work or school
>    account. If this is the first time logging in with this account, you will be prompted to change
>    the password.
>
> For more information on signing up for Microsoft Azure with a work or school account, see [Sign up
> for Microsoft Azure as an Organization](/azure/active-directory/sign-up-organization.md).
>
> For more information about authentication and subscription management in Azure, see
> [Manage Accounts, Subscriptions, and Administrative Roles](/azure/active-directory/role-based-access-control-configure.md).

## Step 3: Run Azure PowerShell cmdlets

Once you have signed in to an Azure account, you can use the Azure PowerShell cmdlets to access and
manager the resources in your subscription.

### Commands to help you get started

```powershell
# To log in to Azure Resource Manager
Login-AzureRmAccount

# You can also use a specific Tenant if you would like a faster log in experience
# Login-AzureRmAccount -TenantId xxxx

# To view all subscriptions for your account
Get-AzureRmSubscription

# To select a default subscription for your current session.
# This is useful when you have multiple subscriptions.
Get-AzureRmSubscription -SubscriptionName "your sub" | Select-AzureRmSubscription

# View your current Azure PowerShell session context
# This session state is only applicable to the current session and will not affect other sessions
Get-AzureRmContext

# To select the default storage context for your current session
Set-AzureRmCurrentStorageAccount -ResourceGroupName "your resource group" -StorageAccountName "your storage account name"

# View your current Azure PowerShell session context
# Note: the CurrentStorageAccount is now set in your session context
Get-AzureRmContext

# To list all of the blobs in all of your containers in all of your accounts
Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

### View account and subscription details

You can have multiple accounts and subscriptions available for use by Azure PowerShell. You can add
multiple accounts by running `Add-AzureRmAccount` more than once.

To display the available Azure accounts, type `Get-AzureAccount`.

To display your Azure subscriptions, type `Get-AzureRmSubscription`.

## <a id="Help"></a>Getting help

These resources provide help for specific cmdlets:

* From within the console, you can use the built-in Help system. The `Get-Help` cmdlet provides
  access to this system.
* For help from the community, try these popular forums:
    + [Azure forum on MSDN](http://go.microsoft.com/fwlink/p/?LinkId=320212)
    + [Stackoverflow](http://go.microsoft.com/fwlink/?LinkId=320213)

## Azure PowerShell Versioning

Azure PowerShell uses Semantic Versioning, which means that if version A > version B, then version A
has the most up-to-date APIs. Also, it means that changes in the major version mean a breaking
change in one or more cmdlets. So, for example, version 1.7.0 is a hotfix to address a breaking
change in the 1.x versions of Azure PowerShell.

For more information about Semantic Versioning practices in Azure PowerShell, see the Semantic
Versioning Specification at: [http://semver.org](http://semver.org)

You should install the latest version available. But if you have scripts written against an earlier
version you should check for breaking changes in the newer version.

* Information about latest version can be found at:
  [https://github.com/Azure/azure-powershell/releases/latest](https://github.com/Azure/azure-powershell/releases/latest).
* Release notes for migrating to a newer release can be found at:
  [https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes](https://github.com/Azure/azure-powershell/tree/dev/documentation/release-notes).

## Azure PowerShell Modules

Azure PowerShell cmdlets provide support for the following Azure services:

* [Azure Resource Manager](/powershell/resourcemanager/)

    Azure Resource Manager enables you to work with the resources in your solution as a group. You can
    deploy, update, or delete all the resources for your solution in a single, coordinated operation.

* [Azure Service Management](/powershell/servicemanagement/)

    Azure Service Management helps you manage your deployments, hosted services, and storage accounts.

* [Azure Storage](/powershell/storage/)

    Azure Storage is the cloud storage solution for modern applications that rely on durability,
    availability, and scalability to meet your needs. Storage supports Blob storage, File storage, Queue
    storage, and Table storage.

### Installing module versions side-by-side

Version 2.1.0 (and version 1.2.6 for AzureStack) are the first module versions designed to be
installed and used side-by-side. Because Azure PowerShell uses binary modules, you must open a new
PowerShell window and use `Import-Module` to import a specific version of the AzureRM cmdlets:

```powershell
Import-Module AzureRM -RequiredVersion 2.1.0**
```

Versions before 2.1.0 (other than 1.2.6) do not work well side-by-side with other Azure PowerShell
module versions. When loading an earlier version of the Azure PowerShell modules using a command
like the one above, incompatible versions of the **AzureRM.Profile** module will be loaded,
resulting in the cmdlets asking you to log in whenever you execute a cmdlet, even after you have
logged in.

The easiest way to resolve this is to install the latest Azure PowerShell from the WebPI feed or
.msi - this removes earlier versions of the modules installed from the gallery.

Note that both Azure and AzureRM modules have dependencies in common, so if you use both modules,
when updating one, you should update both. Earlier versions of the Azure module have the same issue
with side-by-side module loading that earlier versions of the AzureRM module have.

## Azure PowerShell WebPI Installer

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

## Learn More

See the following resources to learn more about using the cmdlets:

* For basic instructions about using Windows PowerShell, see
  [Using Windows PowerShell](https://msdn.microsoft.com/powershell/scripting/getting-started/fundamental/using-windows-powershell).
* For sample scripts and instructions to help you learn to use scripting to manage Azure, see the
  [Script Center](https://gallery.technet.microsoft.com/scriptcenter/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=WindowsAzure&f%5B0%5D.Text=Windows%20Azure).
