---
ms.assetid: F6C78215-4084-4E5F-B689-6380A5958F1A
ms.title: Azure PowerShell Versioning | Microsoft Docs
ms.prod: azure
ms.service: powershell
author: twitchax
ms.author: aaroney
ms.manager: carmonm
---

# Azure PowerShell Modules

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