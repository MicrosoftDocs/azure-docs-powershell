---
title: Overview of Azure PowerShell modules | Microsoft Docs
description: An introduction to the PowerShell modules available to manage Azure resources.
services: azure
author: sdwheeler
manager: carmonm
ms.assetid: ee92f7b5-b84e-4939-a516-709b6abb0fa7
ms.product: azure
ms.service: powershell
ms.devlang: powershell
ms.topic: reference
ms.date: 03/09/2017
ms.author: sewhee
---

# Options for managing Azure using PowerShell

There are several PowerShell module packages available to assist you with management of your Azure
resources. These Azure PowerShell modules allow you to automate repetitive IT admin tasks to save
you time and resources.

## Azure Resource Manager

[Azure Resource Manager](/azure/azure-resource-manager/resource-group-overview) enables you to work
with the resources in your solution as a group. You can deploy, update, or delete all the resources
for your solution in a single, coordinated operation. You use a template for deployment and that
template can work for different environments such as testing, staging, and production. Resource
Manager provides security, auditing, and tagging features to help you manage your resources after
deployment. Azure Resource Manager is the preferred deployment model. This module allows you to
manage your Azure resources using this model.

## Azure Active Directory

Azure Active Directory PowerShell is the primary interface for managing Azure Active Directory.
These cmdlets provide capabilities to retrieve data from the directory, create new objects in the
directory, or change existing objects and configure the directory and its features.

There are two PowerShell modules. The newer AzureAD v2 module and the older MSOnline module. The
MSOnline module is used for functionality that is not yet available in the AzureAD module. If you
are developing new PowerShell scripts with Azure AD cmdlets you should use the newer AzureAD v2
cmdlets whenever possible. The older MSOnline module will be deprecated when all of the
functionality of that module has been migrated to the newer AzureAD module.

## Learn more

To use these cmdlets, you should have a good understanding of PowerShell and how it works. You
should also have some experience with Microsoft Azure as the cmdlets you will use perform the same
functions available through the portal GUI. You’ll also need to know basic PowerShell scripting
techniques.

If you need to brush up on PowerShell before you get started, see
[Scripting with PowerShell](https://technet.microsoft.com/library/bb978526.aspx).

You can also watch this video:
[PowerShell Basics: (Part 1) Getting Started with PowerShell](https://channel9.msdn.com/Blogs/Taste-of-Premier/azps-conceptsBasicsPart1).

If you are new to Azure, see [the Azure documentation](https://docs.microsoft.com/azure/).

Watch this video:
[Take Control of the Cloud with the Microsoft Azure PowerShell Cmdlets](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/WAD-B305#fbid=).
