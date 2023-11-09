---
title: Create an Azure service principal with Azure PowerShell
description: Learn how to create a service principal for your app or service with Azure PowerShell.
keywords: Azure PowerShell, Azure Active Directory, Azure Active directory, AD, RBAC
ms.devlang: powershell
ms.topic: conceptual

ms.custom: devx-track-azurepowershell
---
# Create an Azure service principal with Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

If you plan to manage your app or service with Azure PowerShell, you should run it under an Azure
Microsoft Entra service principal, rather than your own credentials. This article steps you
through creating a security principal with Azure PowerShell.

> [!NOTE]
> You can also create a service principal through the Azure portal. Read
> [Use portal to create Active Directory application and service principal that can access resources](/azure/azure-resource-manager/resource-group-create-service-principal-portal)
> for more details.

## What is a 'service principal'?

An Azure service principal is a security identity used by user-created apps, services, and
automation tools to access specific Azure resources. Think of it as a 'user identity' (username and
password or certificate) with a specific role, and tightly controlled permissions. A service
principal should only need to do specific things, unlike a general user identity. It improves
security if you only grant it the minimum permissions level needed to perform its management tasks.

## Verify your own permission level

First, you must have sufficient permissions in both your Microsoft Entra ID and your Azure
subscription. You must be able to create an app in the Active Directory and assign a role to the
service principal.

The easiest way to check whether your account has the right permissions is through the portal. See
[Check required permission in portal](/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions).

## Create a service principal for your app

Once signed in to your Azure account, you can create the service principal. You must have one
of the following ways to identify your deployed app:

* The unique name of your deployed app, such as "MyDemoWebApp" in the following examples, or
* the Application ID, the unique GUID associated with your deployed app, service, or object

### Get information about your application

The `Get-AzureRmADApplication` cmdlet can be used to get information about your application.

```azurepowershell
Get-AzureRmADApplication -DisplayNameStartWith MyDemoWebApp
```

```Output
DisplayName             : MyDemoWebApp
ObjectId                : 775f64cd-0ec8-4b9b-b69a-8b8946022d9f
IdentifierUris          : {http://MyDemoWebApp}
HomePage                : http://www.contoso.com
Type                    : Application
ApplicationId           : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
AvailableToOtherTenants : False
AppPermissions          :
ReplyUrls               : {}
```

### Create a service principal for your application

The `New-AzureRmADServicePrincipal` cmdlet is used to create the service principal.

```azurepowershell
$servicePrincipal = New-AzureRmADServicePrincipal -ApplicationId 00c01aaa-1603-49fc-b6df-b78c4e5138b4
```

```Output
Secret                : System.Security.SecureString
ServicePrincipalNames : {00c01aaa-1603-49fc-b6df-b78c4e5138b4, http://MyDemoWebApp}
ApplicationId         : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
DisplayName           : MyDemoWebApp
Id                    : 698138e7-d7b6-4738-a866-b4e3081a69e4
AdfsId                :
Type                  : ServicePrincipal
```

From here, you can either directly use the $servicePrincipal.Secret property in
Connect-AzureRmAccount (see "Sign in using the service principal" below), or you can convert this
SecureString to a plain text string for later usage:

```powershell
$BSTR = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($servicePrincipal.Secret)
$password = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($BSTR)
[Runtime.InteropServices.Marshal]::ZeroFreeBSTR($BSTR)
```

### Sign in using the service principal

You can now sign in as the new service principal for your app using the *appId* you provided and
*password* that was automatically generated. You also need the Tenant ID for the service principal.
Your Tenant ID is displayed when you sign into Azure with your personal credentials. To sign in with
a service principal, use the following commands:

```azurepowershell-interactive
$cred = New-Object System.Management.Automation.PSCredential ("00c01aaa-1603-49fc-b6df-b78c4e5138b4", $servicePrincipal.Secret)
Connect-AzureRmAccount -Credential $cred -ServicePrincipal -TenantId 00000000-0000-0000-0000-000000000000
```

After a successful sign-in you see output like:

```Output
Environment           : AzureCloud
Account               : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
TenantId              : 00000000-0000-0000-0000-000000000000
SubscriptionId        :
SubscriptionName      :
CurrentStorageAccount :
```

Congratulations! You can use these credentials to run your app. Next, you need to adjust the
permissions of the service principal.

## Managing roles

> [!NOTE]
> Azure Role-Based Access Control (RBAC) is a model for defining and managing roles for user and
> service principals. Roles have sets of permissions associated with them, which determine the
> resources a principal can read, access, write, or manage. For more information on RBAC and roles,
> see [RBAC: Built-in roles](/azure/active-directory/role-based-access-built-in-roles).

Azure PowerShell provides the following cmdlets to manage role assignments:

* [Get-AzureRmRoleAssignment](/powershell/module/azurerm.resources/get-azurermroleassignment)
* [New-AzureRmRoleAssignment](/powershell/module/azurerm.resources/new-azurermroleassignment)
* [Remove-AzureRmRoleAssignment](/powershell/module/azurerm.resources/remove-azurermroleassignment)

The default role for a service principal is **Contributor**. It may not be the best choice
depending on the scope of your app's interactions with Azure services, given its broad permissions.
The **Reader** role is more restrictive and can be a good choice for read-only apps. You can view
details on role-specific permissions or create custom ones through the Azure portal.

In this example, we add the **Reader** role to our prior example, and delete the **Contributor**
one:

```azurepowershell
New-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4 -RoleDefinitionName Reader
```

```Output
RoleAssignmentId   : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Microsoft.Authorization/roleAssignments/818892f2-d075-46a1-a3a2-3a4e1a12fcd5
Scope              : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG
DisplayName        : MyDemoWebApp
SignInName         :
RoleDefinitionName : Reader
RoleDefinitionId   : b24988ac-6180-42a0-ab88-20f7382dd24c
ObjectId           : 698138e7-d7b6-4738-a866-b4e3081a69e4
ObjectType         : ServicePrincipal
```

```azurepowershell
Remove-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4 -RoleDefinitionName Contributor
```

To view the current roles assigned:

```azurepowershell
Get-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4
```

```Output
RoleAssignmentId   : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Microsoft.Authorization/roleAssignments/0906bbd8-9982-4c03-8dae-aeaae8b13f9e
Scope              : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG
DisplayName        : MyDemoWebApp
SignInName         :
RoleDefinitionName : Reader
RoleDefinitionId   : acdd72a7-3385-48ef-bd42-f606fba81ae7
ObjectId           : 698138e7-d7b6-4738-a866-b4e3081a69e4
ObjectType         : ServicePrincipal
```

Other Azure PowerShell cmdlets for role management:

* [Get-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Get-AzureRmRoleDefinition)
* [New-AzureRmRoleDefinition](/powershell/module/azurerm.resources/New-AzureRmRoleDefinition)
* [Remove-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Remove-AzureRmRoleDefinition)
* [Set-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Set-AzureRmRoleDefinition)

## Change the credentials of the security principal

It's a good security practice to review the permissions and update the password regularly. You may
also want to manage and modify the security credentials as your app changes. For example, we can
change the password of the service principal by creating a new password and removing the old one.

### Add a new password for the service principal

```azurepowershell
New-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```Output
Secret    : System.Security.SecureString
StartDate : 11/16/2018 12:38:23 AM
EndDate   : 11/16/2019 12:38:23 AM
KeyId     : 6f801c3e-6fcd-42b9-be8e-320b17ba1d36
Type      : Password
```

### Get a list of credentials for the service principal

```azurepowershell
Get-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```Output
StartDate           EndDate             KeyId                                Type
---------           -------             -----                                ----
3/8/2017 5:58:24 PM 3/8/2018 5:58:24 PM 6f801c3e-6fcd-42b9-be8e-320b17ba1d36 Password
5/5/2016 4:55:27 PM 5/5/2017 4:55:27 PM ca9d4846-4972-4c70-b6f5-a4effa60b9bc Password
```

### Remove the old password from the service principal

```azurepowershell
Remove-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp -KeyId ca9d4846-4972-4c70-b6f5-a4effa60b9bc
```

```Output
Confirm
Are you sure you want to remove credential with keyId '6f801c3e-6fcd-42b9-be8e-320b17ba1d36' for
service principal objectId '698138e7-d7b6-4738-a866-b4e3081a69e4'.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

### Verify the list of credentials for the service principal

```azurepowershell
Get-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```output
StartDate           EndDate             KeyId                                Type
---------           -------             -----                                ----
3/8/2017 5:58:24 PM 3/8/2018 5:58:24 PM 6f801c3e-6fcd-42b9-be8e-320b17ba1d36 Password
```

### Get information about the service principal

```azurepowershell
$svcprincipal = Get-AzureRmADServicePrincipal -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4
$svcprincipal | Select-Object -Property *
```

```Output
ServicePrincipalNames : {http://MyDemoWebApp, 00c01aaa-1603-49fc-b6df-b78c4e5138b4}
ApplicationId         : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
DisplayName           : MyDemoWebApp
Id                    : 698138e7-d7b6-4738-a866-b4e3081a69e4
Type                  : ServicePrincipal
```
