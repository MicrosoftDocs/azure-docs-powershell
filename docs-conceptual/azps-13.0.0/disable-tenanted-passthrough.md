---
description: Learn about disabling tenanted passthrough for Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Tenanted Passthrough Is Going to be Disabled for Azure PowerShell
---

# Tenanted Passthrough Is Going to be Disabled for Azure PowerShell

To enhance the security, Azure PowerShell are going to disable the users from other organizations or Microsoft account (consumers) to sign in with Azure PowerShell to the tenants where they aren't invited as guests.

If you would like to sign in to a tenant which they are not invited as the guest
You will see following error message in the web browser:

>Selected user account does not exist in tenant '$YourTenantName' and cannot access the application '1950a258-227b-4e31-a9cf-717495945fc2(Microsoft Azure PowerShell) ' in that tenant. The account needs to be added as an external user in the tenant first. Please use a different account.

In order to log in a tenant, make sure the user is either
- a member of that tenant
- a guest invited to that tenant
### Check whether you are the member of the tenant
Suppose your account name is "username@email.com" and tenant Id is "$tenantId"
Please run
```
Connect-AzAccount -AccountId "username@email.com"
Get-AzTenant
```
When you get the list of the tenants, please check whether "$tenantId" is in it. If not or even the list is empty, you should ask the tenant admin to invite you.
### Invite a guest member
If you are a tenant member, you are able to [invite a guest member](https://learn.microsoft.com/en-us/entra/external-id/b2b-quickstart-add-guest-users-portal) to your tenant. The guest user will receive an email invitation to join the tenant. Once they accept the invitation, they will be added as a guest user and can access the tenant's resources.

> [!NOTE]
> The change will affect all the Azure PowerShell versions

