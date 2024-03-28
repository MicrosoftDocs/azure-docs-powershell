---
description: Learn what's new in Azure PowerShell | Microsoft Docs
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: overview
title: What's new in Azure PowerShell
---

# What's new in Azure PowerShell

This page highlights new features, articles, and learning paths for Azure PowerShell.

## Protect sensitive information

Beginning in [Azure PowerShell 11.4.0][az11.4.0-releasenotes], a warning message can be displayed
when reference commands result in the output of sensitive information. For more information, see
[Protect secrets in Azure PowerShell][protect-secrets].

## Sign in with Web Account Manager (WAM)

Azure PowerShell now offers preview support for sign-in with Web Account Manager (WAM). Read about
the benefits of WAM and how to enable the feature in [Sign in with Web Account Manager][wam].

## Upgrade notifications

In-tool notifications for Azure PowerShell version upgrades are a feature released in Az 10.3.0 and
enabled by default in Az 11.0.0. When a new version of Azure PowerShell is available, an upgrade
notification is displayed in your interactive PowerShell session. For more information, see
[Upgrade notifications][upgrade-notifications].

## General availability of modules

### Az.ElasticSan

Azure PowerShell version 11.3.0 introduced the general availability for module Az.ElasticSan. For a
list of commands included in the Az.ElasticSan PowerShell module, see
[Az.ElasticSan][az.elasticsan].

### Az.Nginx

Azure PowerShell version 11.3.0 introduced the general availability for module Az.Nginx. For a list
of commands included in the Az.Nginx PowerShell module, see [Az.Nginx][az.nginx].

### Az.StackHCIVM

Azure PowerShell version 11.3.0 introduced the general availability for module Az.StackHCIVM. For a
list of commands included in the Az.StackHCIVM PowerShell module, see
[Az.StackHCIVM][az.stackhcivm].

### Az.App

Azure PowerShell version 11.0.0 introduced the general availability for module Az.App. For a list of
commands included in the Az.App PowerShell module, see [Az.app][az.app].

### Az.DevCenter

Azure PowerShell version 11.0.0 introduced the general availability for module Az.DevCenter. For a
list of commands included in the Az.DevCenter PowerShell module, see [Az.DevCenter][az.devcenter].

### Az.NetworkCloud

Azure PowerShell version 11.0.0 introduced the general availability for module Az.NetworkCloud. For
a list of commands included in the Az.NetworkCloud PowerShell module, see
[Az.NetworkCloud][az.networkcloud].

## Removed outdated Linux image aliases

Removed unversioned and outdated Linux image aliases of `CentOS`, `Debian`, `RHEL`, and `UbuntuLTS`
in Az 11.0.0 (Az.Compute 7.0.0). Use the aliases `CentOS85Gen2`, `Debian11`, `RHELRaw8LVMGen2`,
`Ubuntu2204` instead.

## Deprecation of AzureRM

Because Az PowerShell modules now have all the capabilities of AzureRM PowerShell modules and more,
we've deprecated the AzureRM PowerShell modules as of February 29, 2024.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

To avoid service interruptions, [update your scripts](https://aka.ms/azpsmigrate) that use AzureRM
PowerShell modules to use Az PowerShell modules. To automatically update your scripts, follow the
[quickstart guide](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

<!-- link references -->

[az11.4.0-releasenotes]: /powershell/azure/release-notes-azureps#1140---march-2024
[protect-secrets]: protect-secrets.md
[wam]: authenticate-interactive.md#web-account-manager-wam
[upgrade-notifications]: configure-global-settings.md#upgrade-notifications
[az.app]:/powershell/module/az.app
[az.devcenter]: /powershell/module/az.devcenter
[az.elasticsan]: /powershell/module/az.elasticsan
[az.nginx]: /powershell/module/az.nginx
[az.stackhcivm]: /powershell/module/az.stackhcivm
[az.networkcloud]: /powershell/module/az.networkcloud
