---
description: Learn the different authentication types for Azure PowerShell — sign in interactively, with a service principal, or with managed identities for Azure resources.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Sign into Azure from Azure PowerShell
---

# Sign into Azure from Azure PowerShell

Azure PowerShell supports several authentication methods. This article describes the authentication
methods for signing into Azure from Azure PowerShell. The method you choose depends on your use
case.

For example, if you're using Azure PowerShell for ad hoc management of Azure resources, you can sign
in using an interactive login. If you're writing a script for automation, you can sign in with a
service principal. If you're running Azure PowerShell in an Azure resource, you can sign in with a
managed identity.

## Authentication methods

Azure PowerShell supports signing in to Azure interactively for a more intuitive and flexible user
experience or noninteractively for automation scenarios. For more information, see the linked
articles.

- [Interactive authentication][authenticate-interactive]
- [Noninteractive authentication][authenticate-noninteractive]

[!INCLUDE [mfa-requirement](../../includes/mfa-requirement.md)]

In addition to these authentication methods, you can also use Azure PowerShell in
[Azure Cloud Shell][azure-cloud-shell], which logs you in automatically. It's the easiest way to get
started with Azure PowerShell.

To keep your Azure resources secure, restrict permissions of the identity for the authentication
method you've chosen using the principle of least privilege. Limiting sign-in permissions as much as
possible for your use case helps keep your Azure resources secure. For more information, see
[Enhance security with the principle of least privilege][principle-of-least-privilege].

## Select your Azure subscription

Once you sign in, Azure PowerShell commands run against your default Azure subscription. If you have
multiple subscriptions, use the `Set-AzContext` cmdlet to select the appropriate subscription. For
more information, see [Use multiple Azure subscriptions][use-multiple-subscriptions].

## Refresh tokens

When you sign in with a user account, Azure PowerShell generates and stores an authentication
refresh token. Because access tokens are valid for only a short period of time, a refresh token is
issued at the same time the access token is issued. The client application can exchange this refresh
token for a new access token when needed.

> [!NOTE]
> Depending on your authentication method, your tenant may have Conditional Access policies
> restricting your access to certain resources.

For more information, see [Refresh tokens in the Microsoft identity platform][refresh-tokens].

## See also

- [Azure PowerShell context objects](context-persistence.md)
- [Create an Azure service principal with Azure PowerShell](create-azure-service-principal-azureps.md)
- [Set-AzContext][select-azcontext]

<!-- link references -->
[azure-cloud-shell]: /azure/cloud-shell/overview
[authenticate-interactive]: authenticate-interactive.md
[authenticate-noninteractive]: authenticate-noninteractive.md
[principle-of-least-privilege]: /entra/identity-platform/secure-least-privileged-access
[use-multiple-subscriptions]: /powershell/azure/manage-subscriptions-azureps
[select-azcontext]: /powershell/module/az.accounts/set-azcontext
[refresh-tokens]: /entra/identity-platform/refresh-tokens
