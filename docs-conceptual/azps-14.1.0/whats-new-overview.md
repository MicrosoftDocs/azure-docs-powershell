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

[!INCLUDE [mfa-requirement](../../includes/mfa-requirement.md)]

## Protect sensitive information

Azure PowerShell displays a warning message by default beginning with Az version 12.0.0 to help you
protect sensitive information when it identifies a potential secret in the output of a command. For
more information, see [Protect secrets in Azure PowerShell][protect-secrets].

## Sign in with Web Account Manager (WAM)

Beginning with Az PowerShell module version 12.0.0, Azure PowerShell's default login authentication
method for Windows-based systems is Web Account Manager (WAM). For more information, see
[Web Account Manager (WAM)][wam].

## New login experience

Beginning with Az PowerShell module version 12.0.0, if you have access to multiple subscriptions,
you're prompted to select an Azure subscription to login with. For more information, see
[Login experience][login-experience].

## Support lifecycle

Beginning with Az PowerShell module version 12.0.0, Azure PowerShell ships two types of generally
available releases. Customers can choose Standard Term Support (STS) or Long Term Support (LTS)
releases. The quality of all releases is the same. The only difference is the length of support. For
more information, see [Support of releases][support-of-releases].

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

[protect-secrets]: protect-secrets.md
[wam]: authenticate-interactive.md#web-account-manager-wam
[login-experience]: authenticate-interactive.md#login-experience
[support-of-releases]: azureps-support-lifecycle.md#support-of-releases
[upgrade-notifications]: configure-global-settings.md#upgrade-notifications
[az.app]:/powershell/module/az.app
[az.devcenter]: /powershell/module/az.devcenter
[az.elasticsan]: /powershell/module/az.elasticsan
[az.nginx]: /powershell/module/az.nginx
[az.stackhcivm]: /powershell/module/az.stackhcivm
[az.networkcloud]: /powershell/module/az.networkcloud
