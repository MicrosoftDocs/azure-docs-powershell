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
[Web Platform Installer (WebPI)](azureps-webpi.md), or the MSI file available from 
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

## Learn More

See the following resources to learn more about using the cmdlets:

* For basic instructions about using Windows PowerShell, see
  [Using Windows PowerShell](https://msdn.microsoft.com/powershell/scripting/getting-started/fundamental/using-windows-powershell).
* For sample scripts and instructions to help you learn to use scripting to manage Azure, see the
  [Script Center](https://gallery.technet.microsoft.com/scriptcenter/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=WindowsAzure&f%5B0%5D.Text=Windows%20Azure).
* For versioning information, see [Azure PowerShell Versioning](azureps-versioning.md).
* For module and side-by-side information, see [Azure PowerShell Modules](azureps-modules.md).
* For WebPI information, see [Azure PowerShell WebPI Installer](azureps-webpi.md).