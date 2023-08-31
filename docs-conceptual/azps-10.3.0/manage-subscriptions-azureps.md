---
description: Manage Azure subscriptions with Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.date: 08/01/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Manage Azure subscriptions with Azure PowerShell
---

# Use multiple Azure subscriptions

Most Azure users only have a single subscription. However, if you are part of more than one
organization or your organization has divided up access to certain resources across groupings, you
may have multiple subscriptions within Azure.

For detailed information on subscriptions, billing, and cost management, see the
[billing and cost management documentation](/azure/billing/).

## Tenants, users, and subscriptions

You might have some confusion over the difference between tenants, users, and subscriptions within
Azure. A _tenant_ is the Azure Active Directory entity that encompasses a whole organization. This
tenant has at least one _subscription_ and _user_. A user is an individual and is associated with
only one tenant, the organization that they belong to. Users are those accounts that sign in to
Azure to create, manage, and use resources. A user may have access to multiple _subscriptions_,
which are the agreements with Microsoft to use cloud services, including Azure. Every resource is
associated with a subscription.

To learn more about the differences between tenants, users, and subscriptions, see the
[Azure cloud terminology dictionary](/azure/azure-glossary-cloud-terminology). To learn how to add a
new subscription to your Azure Active Directory tenant, see
[Associate or add an Azure subscription to your Azure Active Directory tenant](/azure/active-directory/active-directory-how-subscriptions-associated-directory).
To learn how to sign in to a specific tenant, see
[Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

## Change the active subscription

In Azure PowerShell, accessing the resources for a subscription requires changing the subscription
associated with your current Azure session. This is done by modifying the active session context,
the information about which tenant, subscription, and user cmdlets should be run against. In order
to change subscriptions, you use the [Set-AzContext](/powershell/module/az.accounts/set-azcontext)
cmdlet to change the current context.

The following example shows how to change the context in your current Azure session:

```azurepowershell-interactive
Set-AzContext -Subscription <subscription name or id>
```

You can use the [Get-AzSubscription](/powershell/module/az.accounts/get-azsubscription) cmdlet to
retrieve a list of your Azure subscriptions.

To learn more about Azure PowerShell contexts, including how to save them and switch between them
for working with multiple subscriptions, see
[Persist credentials with Azure PowerShell contexts](context-persistence.md).
