---
ms.assetid: 6241F689-7AFE-45F0-A657-514A8D84C18F
ms.title: Azure PowerShell Versioning | Microsoft Docs
ms.prod: azure
ms.service: powershell
author: twitchax
ms.author: aaroney
ms.manager: carmonm
---

# Azure PowerShell Versioning

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