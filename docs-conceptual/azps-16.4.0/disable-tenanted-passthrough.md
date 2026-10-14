---
description: Learn about Azure PowerShell disabling tenanted passthrough to enhance security. Check tenant membership, invite guest users, and resolve login issues.
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
title: Tenanted passthrough is going to be disabled for Azure PowerShell
---

# Tenanted passthrough is going to be disabled for Azure PowerShell

To enhance security, Azure PowerShell is going to block users from other organizations or personal
Microsoft accounts (consumers) from signing in with Azure PowerShell to tenants where they aren't
invited as guests.

> [!NOTE]
> This change affects all Azure PowerShell versions.

If you attempt to sign in to a tenant where you aren't invited as a guest, you see the following
error message in your web browser:

```Output
Selected user account does not exist in tenant '$YourTenantName' and cannot access the application '00000000-0000-0000-0000-000000000000(Microsoft Azure PowerShell)' in that tenant. The account needs to be added as an external user in the tenant first. Please use a different account.
```

To sign in to a tenant, ensure the user is either:

- A member of the tenant
- A guest invited to the tenant

## Check whether you are the member of a tenant

If your username is `someone@example.com` and the tenant ID is `$tenantId`, run the following
commands:

```azurepowershell
Connect-AzAccount -AccountId someone@example.com
Get-AzTenant
```

When you retrieve the list of tenants, determine if `$tenantId` is included. If not, or if the list
is empty, contact the tenant administrator to request an invitation.

## Invite a guest member

As a tenant member, you can [invite a guest user to your tenant][invite-tenant-guest]. The guest
user receives an email invitation to join the tenant. Once the invitation is accepted, they're added
as a guest user and gain access to the tenant's resources.

<!-- link references -->

[invite-tenant-guest]: /entra/external-id/b2b-quickstart-add-guest-users-portal
