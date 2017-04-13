---
Module Name: AzureRM.AzureStackAdmin
Module Guid: 0e691e0a-ce16-40f2-af84-86fb0d82fb29
Download Help Link: {{Please enter FwLink manually}}
Help Version: {{Please enter version of help manually (X.X.X.X) format}}
Locale: en-US
---

# AzureRM.AzureStackAdmin Module
## Description
This topic displays help topics for the PowerShell cmdlets used by the Azure Stack administrator.

## AzureRM.AzureStackAdmin Cmdlets
### [Add-AzureRMGalleryItem](Add-AzureRMGalleryItem.md)
The Add-AzureRMGalleryItem cmdlet adds the gallery item package.
The gallery item uri needs to be a http/https uri accessible to the gallery service. 
Typically .azpkg file is uploaded to a publicly accessible blob container and its uri is provided as the GallelryItemUri parameter

### [Add-AzureRMResourceProviderRegistration](Add-AzureRMResourceProviderRegistration.md)
This cmdlet adds a resource provider manifest to azure stack resource manager.
This is needed to register any new resource provider with resource manager.

### [Add-AzureRMUsageConnection](Add-AzureRMUsageConnection.md)
The Add-AzureRMUsageConnection cmdlet adds an usage connection details for a resource provider.
The cmdlet gets the storage account information where the resource provider is storing the usage records.
This information is given to the usage service through this cmdlet. 
Usage Service will retrieve the usage records periodically from the storage account information provided

### [Get-AzureRMGalleryItem](Get-AzureRMGalleryItem.md)
The Get-AzureRmGalleryItem cmdlet gets the gallery item

### [Get-AzureRMManagedLocation](Get-AzureRMManagedLocation.md)
The Get-AzureRmMangedLocation cmdlet gets the azurestack resource manager location as an administrator

### [Get-AzureRMManagedSubscription](Get-AzureRMManagedSubscription.md)
This enables service administrator to get the tenant target subscription id

### [Get-AzureRMOffer](Get-AzureRMOffer.md)
The cmdlet gets the offer as an administrator or as a tenant user

### [Get-AzureRMPlan](Get-AzureRMPlan.md)
The Get-AzureRmPlan cmdlet gets the plan details

### [Get-AzureRMResourceProviderRegistration](Get-AzureRMResourceProviderRegistration.md)
The Get-AzureRmResourceProviderRegistration cmdlet gets the resource provider manifest registration details

### [Get-AzureRMTenantSubscription](Get-AzureRMTenantSubscription.md)
The Get-AzureRmTenantSubscription gets the subscriptions associated with the current logged in user.

### [Get-AzureRMUsageConnection](Get-AzureRMUsageConnection.md)
The Get-AzureRMUsageConnection cmdlet gets the specified usage connection information

### [Get-AzureStackToken](Get-AzureStackToken.md)
The Get-AzureStackToken cmdlet gets a token to be used to make calls to Azurestack Resource Manager.
The cmdlet will be deprecated in a future release

### [New-AzureRMManagedLocation](New-AzureRMManagedLocation.md)
The cmdlet New-AzureRmManagedLocation creates a new location managed by Azurestack Resource Manager.
The resource providers can be deployed in the new location

### [New-AzureRMManagedSubscription](New-AzureRMManagedSubscription.md)
The New-AzureRmManagedSubscriiption cmdlet creates a subscription as an admin for the specified tenant user

### [New-AzureRMOffer](New-AzureRMOffer.md)
The New-AzureRmOffer cmdlet creates an offer composing of the specified base plans and add ons

### [New-AzureRMPlan](New-AzureRMPlan.md)
The New-AzureRmPlan cmdlet creates a new plan composing the various quotas of the resource provider

### [New-AzureRMTenantSubscription](New-AzureRMTenantSubscription.md)
The cmdlet New-AzureRMTenantSubscription creates a subscription as a tenant for the specified offer

### [Remove-AzureRMGalleryItem](Remove-AzureRMGalleryItem.md)
The Remove-AzureRMGalleryItem cmdlet removes the specified gallery item

### [Remove-AzureRMManagedLocation](Remove-AzureRMManagedLocation.md)
The Remove-AzureRmManagedLocation cmdlet removes the specified location

### [Remove-AzureRMManagedSubscription](Remove-AzureRMManagedSubscription.md)
The cmdlet Remove-AzureRMManagedSubscription removes the specified subscription as an administrator

### [Remove-AzureRMOffer](Remove-AzureRMOffer.md)
The Remove-AzureRmOffer cmdlet removes the specified offer

### [Remove-AzureRMPlan](Remove-AzureRMPlan.md)
The Remove-AzureRMPlan cmddlet removes the specified plan.
The plan should not have any references to offers to get removed

### [Remove-AzureRMResourceProviderRegistration](Remove-AzureRMResourceProviderRegistration.md)
The Remove-ResourceProviderRegistration cmdlet removes the resource provider manifest

### [Remove-AzureRMTenantSubscription](Remove-AzureRMTenantSubscription.md)
The Remove-AzureRMTenantSubscription cmdlet removes the current logged in user's specified subscription.
There should not be any resources under the subscription to be removed

### [Remove-AzureRMUsageConnection](Remove-AzureRMUsageConnection.md)
The Remove-AzureRMUsageConnection cmdlet removes the usage connection information from the usage service.

### [Set-AzureRMManagedLocation](Set-AzureRMManagedLocation.md)
The Set-AzureRMManagedLocation cmdlet modifies the existing location

### [Set-AzureRMManagedSubscription](Set-AzureRMManagedSubscription.md)
The Set-AzureRMManagedSubscription updates any tenant user subscription as a service administrator

### [Set-AzureRMOffer](Set-AzureRMOffer.md)
The Set-AzureRmOffer cmdlet updates the existing offer

### [Set-AzureRMPlan](Set-AzureRMPlan.md)
The cmdlet Set-AzureRMPlan updates the existing plan with the given modified plan object

### [Set-AzureRMResourceProviderRegistration](Set-AzureRMResourceProviderRegistration.md)
Updates the provider registration manifest with the new provider registration model

### [Set-AzureRMTenantSubscription](Set-AzureRMTenantSubscription.md)
The Set-AzureRMTenantSubscription cmdlet updates the current logged user's subscription details.
This cmdlet will be deprecated in a future release

