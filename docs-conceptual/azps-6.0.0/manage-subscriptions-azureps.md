---
title: Manage Azure subscriptions with Azure PowerShell
description: Manage Azure subscriptions with Azure PowerShell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 02/04/2019 
ms.custom: devx-track-azurepowershell 
ms.service: azure-powershell
---
# Use multiple Azure subscriptions

Most Azure users will only ever have a single subscription. However, if you are part of more than one organization or your organization has
divided up access to certain resources across groupings, you may have multiple subscriptions within Azure. The CLI supports selecting a subscription
both globally and per command.

For detailed information on subscriptions, billing, and cost management, see the [billing and cost management documentation](/azure/billing/).

## Tenants, users, and subscriptions

You might have some confusion over the difference between tenants, users, and subscriptions within Azure. A _tenant_ is the Azure Active Directory
entity that encompasses a whole organization. This tenant has at least one _subscription_ and _user_. A user is an individual and is associated
with only one tenant, the organization that they belong to. Users are those accounts that sign in to Azure to create, manage, and use resources.
A user may have access to multiple _subscriptions_, which are the agreements with Microsoft to use cloud services, including Azure. Every resource
is associated with a subscription.

To learn more about the differences between tenants, users, and subscriptions, see the
[Azure cloud terminology dictionary](/azure/azure-glossary-cloud-terminology).  To learn how to add a new subscription to your Azure Active
Directory tenant, see
[Associate or add an Azure subscription to your Azure Active Directory tenant](/azure/active-directory/active-directory-how-subscriptions-associated-directory).
To learn how to sign in to a specific tenant, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

## Change the active subscription

In Azure PowerShell, accessing the resources for a subscription requires changing the subscription associated with your current Azure session.
This is done by modifying the active session context, the information about which tenant, subscription, and user cmdlets should be run against.
In order to change subscriptions, an Azure PowerShell Context object first needs to be retrieved with [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription)
and then the current context changed with [Set-AzContext](/powershell/module/az.accounts/set-azcontext).

The next example shows how to get a subscription in the currently active tenant, and set it as the active session:

```powershell-interactive
$context = Get-AzSubscription -SubscriptionId ...
Set-AzContext $context
```

To learn more about Azure PowerShell contexts, including how to save them and quickly switch between them for working with multiple subscriptions easily, see [Persist credentials with Azure PowerShell contexts](context-persistence.md).
