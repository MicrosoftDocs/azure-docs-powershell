---
title: Get started with Azure PowerShell
description: Get started with Azure PowerShell
ms.devlang: powershell
ms.topic: get-started-article
ms.date: 04/24/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
---

# Get started with Azure PowerShell

Azure PowerShell is designed for managing and administering Azure resources from the command line.
Use Azure PowerShell when you want to build automated tools that use the Azure Resource Manager
model. Try it out in your browser with [Azure Cloud Shell](/azure/cloud-shell/overview), or install
on your local machine.

This article helps you get started with Azure PowerShell and teaches the core concepts behind it.

## Install or run in Azure Cloud Shell

The easiest way to get started with Azure PowerShell is by trying it out in an Azure Cloud Shell
environment. To get up and running with Cloud Shell, see
[Quickstart for PowerShell in Azure Cloud Shell](/azure/cloud-shell/quickstart-powershell). Cloud
Shell runs PowerShell on a Linux container, so Windows-specific functionality isn't available.

When you're ready to install Azure PowerShell on your local machine, follow the instructions in
[Install the Azure PowerShell module](install-az-ps.md).

## Sign in to Azure

Sign in interactively with the
[Connect-AzAccount](/powershell/module/az.accounts/connect-azaccount) cmdlet. Skip this step if you
use Cloud Shell. Your Azure Cloud Shell session is already authenticated for the environment,
subscription, and tenant that launched the Cloud Shell session.

```azurepowershell-interactive
Connect-AzAccount
```

Azure cloud services offer environments compliant with regional data-handling laws. For accounts in
a regional cloud, use the **Environment** parameter to sign in. Get the name of the environment for
your region using the [Get-AzEnvironment](/powershell/module/Az.Accounts/Get-AzEnvironment) cmdlet.
For example, to sign in to Azure China 21Vianet:

```azurepowershell-interactive
Connect-AzAccount -Environment AzureChinaCloud
```

In Windows PowerShell 5.1 environments, you'll receive a sign-in dialog to provide a username and
password for your Azure account. On every other version of PowerShell, you'll get a token to use on
[microsoft.com/devicelogin](https://microsoft.com/devicelogin). Open this page in your browser and
enter the token, then sign in with your Azure account credentials and authorize Azure PowerShell.

After signing in, you'll see information indicating which of your Azure subscriptions is active. If
you have multiple Azure subscriptions in your account and want to select a different one, get your
available subscriptions with
[Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) and use the
[Set-AzContext](/powershell/module/az.accounts/set-azcontext) cmdlet with your subscription ID. For
more information about managing your Azure subscriptions in Azure PowerShell, see
[Use multiple Azure subscriptions](manage-subscriptions-azureps.md).

Once signed in, use the Azure PowerShell cmdlets to access and manage resources in your
subscription. To learn more about the sign-in process and authentication methods, see
[Sign in with Azure PowerShell](authenticate-azureps.md).

## Find commands

Azure PowerShell cmdlets follow a standard naming convention for PowerShell, `Verb-Noun`. The verb
describes the action (examples include `New`, `Get`, `Set`, `Remove`) and the noun describes the
resource type (examples include `AzVM`, `AzKeyVaultCertificate`, `AzFirewall`,
`AzVirtualNetworkGateway`). Nouns in Azure PowerShell always start with the prefix `Az`. For the
full list of standard verbs, see
[Approved verbs for PowerShell Commands](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands).

Knowing the nouns, verbs, and the Azure PowerShell modules available helps you find commands with
the [Get-Command](/powershell/module/microsoft.powershell.core/get-command) cmdlet. For example, to
find all VM-related commands that use the `Get` verb:

```powershell-interactive
Get-Command -Verb Get -Noun AzVM* -Module Az.Compute
```

To help you find common commands, this table lists the resource type, corresponding Azure PowerShell
module, and noun prefix to use with `Get-Command`:

|                              Resource type                              |                   Azure PowerShell module                    |    Noun prefix     |
| ----------------------------------------------------------------------- | ------------------------------------------------------------ | ------------------ |
| [Resource group](/azure/azure-resource-manager/resource-group-overview) | [Az.Resources](/powershell/module/az.resources#resources)    | `AzResourceGroup`  |
| [Virtual machines](/azure/virtual-machines)                             | [Az.Compute](/powershell/module/az.compute#virtual_machines) | `AzVM`             |
| [Storage accounts](/azure/storage/common/storage-introduction)          | [Az.Storage](/powershell/module/az.storage/)                 | `AzStorageAccount` |
| [Key Vault](/azure/key-vault/key-vault-whatis)                          | [Az.KeyVault](/powershell/module/az.keyvault)                | `AzKeyVault`       |
| [Web applications](/azure/app-service)                                  | [Az.Websites](/powershell/module/az.websites)                | `AzWebApp`         |
| [SQL databases](/azure/sql-database)                                    | [Az.Sql](/powershell/module/az.sql)                          | `AzSqlDatabase`    |

For a full list of the modules in Azure PowerShell, see the
[Azure PowerShell modules list](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md)
hosted on GitHub.

## Telemetry

Azure PowerShell automatically collects telemetry data by default. Microsoft aggregates collected
data to identify patterns of usage, to identify common issues, and to improve the experience of
Azure PowerShell. Microsoft Azure PowerShell doesn't collect any private or personal data. To
disable data collection, you must explicitly opt out by executing
[Disable-AzDataCollection](/powershell/module/az.accounts/disable-azdatacollection).

## Learn Azure PowerShell basics with quickstarts and tutorials

To get started with Azure PowerShell, try an in-depth tutorial for setting up virtual machines and
learning how to query them.

> [!div class="nextstepaction"]
> [Create virtual machines with Azure PowerShell](azureps-vm-tutorial.yml)

There are also Azure PowerShell quickstarts for other popular Azure services:

* [Create a storage account](/azure/storage/common/storage-quickstart-create-account?tabs=azure-powershell)
* [Transfer objects to/from Azure Blob storage](/azure/storage/blobs/storage-quickstart-blobs-powershell)
* [Create and retrieve secrets from Azure Key Vault](/azure/key-vault/quick-create-powershell)
* [Create an Azure SQL database and firewall](/azure/sql-database/scripts/sql-database-create-and-configure-database-powershell)
* [Run a container in Azure Container Instances](/azure/container-instances/container-instances-quickstart-powershell)
* [Create a Virtual Machine Scale Set](/azure/virtual-machine-scale-sets/quick-create-powershell)
* [Create a standard load balancer](/azure/load-balancer/quickstart-create-standard-load-balancer-powershell)

## Next steps

* [Sign in with Azure PowerShell](authenticate-azureps.md)
* [Manage Azure subscriptions with Azure PowerShell](manage-subscriptions-azureps.md)
* [Create service principals with Azure PowerShell](create-azure-service-principal-azureps.md)
* Get help from the community:
  * [Azure forum on MSDN](https://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [Stack Overflow](https://go.microsoft.com/fwlink/?LinkId=320213)
