# Azure Resource Manager Cmdlets

This section displays the online help files for the Azure Resource Manager in Azure PowerShell 3.0.
The cmdlets in the __AzureRM.*__ modules let you use Resource Manager in Azure PowerShell.

## Changes for the Azure PowerShell 3.0 release

These are the breaking changes for Azure PowerShell 3.0.
For additional details, see [Breaking changes for Microsoft Azure PowerShell 3.0.0](https://github.com/Azure/azure-powershell/blob/v3.0.0-September2016/documentation/release-notes/migration-guide.3.0.0.md) and the cmdlet documentation.

### Breaking changes to Data Lake Store cmdlets

The **Get-AzureRmDataLakeStoreItemAclEntry** cmdlet replaces the **Get-AzureRmDataLakeStoreItemAcl** cmdlet.
**Get-AzureRmDataLakeStoreItemAclEntry** returns a list of entries in the access control list (ACL) of the path.
The deprecated **Get-AzureRmDataLakeStoreItemAcl** returns a complex object that represents the ACL.

You can pass the output of **Get-AzureRmDataLakeStoreItemAclEntry** to the Acl parameter of the following cmdlets:

- **Get-AzureRmDataLakeStoreItemAclEntry**
- **Set-AzureRmDataLakeStoreItemAcl**
- **Set-AzureRmDataLakeStoreItemAclEntry**

### Breaking changes to ApiManagement cmdlets

In the **New-AzureRMApiManagementVirtualNetwork** cmdlet, the parameters used to refer to a virtual network changed from _SubnetName_ and _VnetId_ to _SubnetResourceId_.
Specify a virtual network in the following format:

```PowerShell
/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ClassicNetwork/virtualNetworks/{virtualNetworkName}/subnets/{subnetName}
```

The **Set-AzureRmApiManagementVirtualNetworks** cmdlet has been deprecated.
Instead, use the **New-AzureRMApiManagementVirtualNetwork** and **Update-AzureRMApiManagementDeployment** cmdlets.

### Breaking changes to Network cmdlets

In the **New-AzureRmVirtualNetworkGateway** cmdlet, the _ActiveActive_ **Boolean** parameter has been replaced by the _EnableActiveActiveFeature_ switch parameter.

In the **Set-AzureRmVirtualNetworkGateway** cmdlet, the _ActiveActive_ **Boolean** parameter has been replaced by the _EnableActiveActiveFeature_ and _DisableActiveActiveFeature_ switch parameters.

## To install the cmdlets

To install the cmdlets by using PowerShell Gallery using **PowerShellGet**, you must have Windows Management Framework (WMF) 5.0. For more information, see [Windows Management Framework 5.0 Production Preview](https://www.microsoft.com/en-us/download/details.aspx?id=48729).
By default, WMF 5.0 comes installed on Windows 10.
Run the following commands from the Windows PowerShell console running as Administrator:

```PowerShell
PS C:\> Install-Module AzureRM
PS C:\> Install-AzureRM
```

The first command installs the **AzureRM** module from the PowerShell Gallery.
The second command installs all the component modules of Azure Resource Manager in the module version range specified in the **AzureRM** module.

Azure Resource Manager is broken into component modules.
For example, Azure Resource Management modules for compute services are in module **AzureRM.Compute**.
To import all of the **AzureRM** modules into the current run space run the following commands.

To import all of the __AzureRM.*__ modules within the known semantic version range, run this command:

```PowerShell
PS C:\> Import-AzureRM
```

To import a single **AzureRM** module, specify the module by name, as in the following example for the **AzureRM.Compute** module:

```PowerShell
PS C:\> Import-Module AzureRM.Compute
```

To see all of the Azure Resource Manager modules installed and their versions, run the following command:

```PowerShell
PS C:\> Get-Module –ListAvailable AzureRM*
```

## To use the cmdlets

To start working with the Azure Resource Manager cmdlets, first log on to your Azure account by using the **Add-AzureRMAccount** cmdlet.

After logging into Azure, Azure PowerShell creates a context for the given session.
That context contains the Azure PowerShell environment, account, tenant, and subscription that will be used for all cmdlets within that session. The context can be manipulated by using the **Set-AzureRMContext** or **Select-AzureRmSubscription** cmdlet.
To view your current context, run the following command:

```PowerShell
PS C:\> Get-AzureRmContext
```

To view all subscriptions for your account, run the following command:

```PowerShell
PS C:\> Get-AzureRmSubscription
```

To select a default subscription for your current session, run the following command:

```PowerShell
PS C:\> Get-AzureRmSubscription –SubscriptionName "your subscription" | Select-AzureRmSubscription
```

To select the default storage context for your current session, run the following command:

```PowerShell
PS C:\> Set-AzureRmCurrentStorageAccount –ResourceGroupName "your resource group" –StorageAccountName "your storage account name"
```

To import the **Azure.Storage** data plane module (blob, queue, table), run the following command:

```PowerShell
PS C:\> Import-Module Azure.Storage
```

To list all of the blobs in all of your containers in all of your accounts, run the following command:

```PowerShell
PS C:\> Get-AzureRmStorageAccount | Get-AzureStorageContainer | Get-AzureStorageBlob
```

## See Also

[Azure Resource Manager Overview](http://azure.microsoft.com/en-us/documentation/articles/resource-group-overview/)
