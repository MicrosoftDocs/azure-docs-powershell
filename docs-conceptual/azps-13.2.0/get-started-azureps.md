---
description: Learn how to get started with Azure PowerShell to manage Azure resources, sign in, and find essential cmdlets for automating tasks with ease.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: get-started
title: Get started with Azure PowerShell
---

# Get started with Azure PowerShell

Azure PowerShell is a powerful tool for managing and administering Azure resources directly from
PowerShell. It's ideal for building automated workflows and managing resources using the Azure
Resource Manager model. You can try it out in your browser using [Azure Cloud Shell][cloudshell] or
install it locally on your machine.

This article helps you get started with Azure PowerShell and teaches its core concepts.

## Install or run in Azure Cloud Shell

The easiest way to try Azure PowerShell is through Azure Cloud Shell, a browser-based environment
that requires no installation. To get started, see
[Get started with Azure Cloud Shell][ps-cloudshell]. Cloud Shell runs PowerShell on a Linux
container, so Windows-specific features aren't available.

When you're ready to install Azure PowerShell locally, follow the steps in
[How to install Azure PowerShell][install-azps].

## Sign in to Azure

To sign in, use the `Connect-AzAccount` cmdlet. If you're using Cloud Shell, you can skip this step
since you're already authenticated for your environment, subscription, and tenant.

```azurepowershell
Connect-AzAccount
```

[!INCLUDE [mfa-requirement](../../includes/mfa-requirement.md)]

For regional environments that require specific compliance, for example, Azure China 21Vianet, use
the **Environment** parameter:

```azurepowershell
Connect-AzAccount -Environment AzureChinaCloud
```

Azure PowerShell defaults to Web Account Manager (WAM) for authentication on Windows systems, while
other platforms use browser-based login. For more information, see
[Web Account Manager (WAM)][wam].

If you have access to multiple subscriptions, you're prompted to select one upon login. Learn more
about this process in [Login experience][login-experience].

Once signed in, you can use Azure PowerShell cmdlets to manage your resources. For more information
on authentication, see [Sign in with Azure PowerShell][authenticate].

## Find commands

Azure PowerShell cmdlets follow the standard PowerShell naming convention of `Verb-Noun`. The verb
describes the action, for instance, `New`, `Get`, `Set`, and `Remove`, while the noun represents the
resource type, for example, `AzVM`, `AzKeyVaultCertificate`, `AzFirewall`, and
`AzVirtualNetworkGateway`. Nouns in Azure PowerShell start with the prefix `Az`.

To discover commands, use the `Get-Command` cmdlet. For instance, to list all commands related to
virtual machines:

```powershell-interactive
Get-Command -Verb Get -Noun AzVM* -Module Az.Compute
```

Here's a quick reference table of common resources and their associated modules:

|  Resource Type   | Azure PowerShell Module |   Noun Prefix    |
| ---------------- | ----------------------- | ---------------- |
| Resource Groups  | Az.Resources            | AzResourceGroup  |
| Virtual Machines | Az.Compute              | AzVM             |
| Storage Accounts | Az.Storage              | AzStorageAccount |
| Key Vault        | Az.KeyVault             | AzKeyVault       |
| Web Applications | Az.Websites             | AzWebApp         |
| SQL Databases    | Az.Sql                  | AzSqlDatabase    |

For a complete list of Azure PowerShell modules, see the
[Azure PowerShell modules list][azps-modules] hosted on GitHub.

## Data collection

By default, Azure PowerShell collects telemetry data to improve user experience by identifying usage
patterns and issues. No private or personal data is collected. However, you can opt out using the
`Disable-AzDataCollection` cmdlet if you prefer. For more information, see our
[privacy statement][privacy-statement].

## Quickstarts and tutorials

Get hands-on with Azure PowerShell through our guided tutorials:

- [Create virtual machines with Azure PowerShell][create-vms]
- [Create a storage account][create-storageaccount]
- [Transfer objects to/from Azure Blob storage][transfer-objects]
- [Create and retrieve secrets from Azure Key Vault][keyvault]
- [Create an Azure SQL database and firewall][azsql]
- [Run a container in Azure Container Instances][aci]
- [Create a Virtual Machine Scale Set][vm-scaleset]
- [Create a standard load balancer][load-balancer]

## Next steps

Explore more Azure PowerShell capabilities:

- [Sign in with Azure PowerShell][authenticate]
- [Manage Azure subscriptions with Azure PowerShell][manage-subscriptions]
- [Create service principals with Azure PowerShell][service-principal]

For more help, connect with the community:

- [Azure Tools Community][aztools-community]
- [Stack Overflow][stack-overflow]

## References

- [Connect-AzAccount][connect-azaccount]
- [Get-AzEnvironment][get-azenvironment]
- [Get-Command][get-command]
- [Disable-AzDataCollection][disable-azdatacollection]

<!-- link references -->

[cloudshell]: /azure/cloud-shell/overview
[ps-cloudshell]: /azure/cloud-shell/quickstart-powershell
[install-azps]: install-azure-powershell.md
[connect-azaccount]: /powershell/module/az.accounts/connect-azaccount
[get-azenvironment]: /powershell/module/Az.Accounts/Get-AzEnvironment
[wam]: authenticate-interactive.md#web-account-manager-wam
[login-experience]: authenticate-interactive.md#login-experience
[authenticate]: authenticate-azureps.md
[get-command]: /powershell/module/microsoft.powershell.core/get-command
[azps-modules]: https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md
[disable-azdatacollection]: /powershell/module/az.accounts/disable-azdatacollection
[privacy-statement]: https://privacy.microsoft.com/privacystatement
[create-vms]: azureps-vm-tutorial.yml
[create-storageaccount]: /azure/storage/common/storage-quickstart-create-account?tabs=azure-powershell
[transfer-objects]: /azure/storage/blobs/storage-quickstart-blobs-powershell
[keyvault]: /azure/key-vault/quick-create-powershell
[azsql]: /azure/sql-database/scripts/sql-database-create-and-configure-database-powershell
[aci]: /azure/container-instances/container-instances-quickstart-powershell
[vm-scaleset]: /azure/virtual-machine-scale-sets/quick-create-powershell
[load-balancer]: /azure/load-balancer/quickstart-create-standard-load-balancer-powershell
[service-principal]: create-azure-service-principal-azureps.md
[aztools-community]: https://techcommunity.microsoft.com/t5/azure-tools/bd-p/AzureTools
[stack-overflow]: https://go.microsoft.com/fwlink/?LinkId=320213
[manage-subscriptions]: /powershell/azure/manage-subscriptions-azureps
