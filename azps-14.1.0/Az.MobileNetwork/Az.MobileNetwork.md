---
Module Name: Az.MobileNetwork
Module Guid: 11f61d2d-3318-4e19-8917-0f0bd2cc78c7
Download Help Link: https://learn.microsoft.com/powershell/module/az.mobilenetwork
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Az.MobileNetwork.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MobileNetwork/MobileNetwork/help/Az.MobileNetwork.md
---

# Az.MobileNetwork Module
## Description
Microsoft Azure PowerShell: MobileNetwork cmdlets

## Az.MobileNetwork Cmdlets
### [Deploy-AzMobileNetworkReinstallPacketCoreControlPlane](Deploy-AzMobileNetworkReinstallPacketCoreControlPlane.md)
Reinstall the specified packet core control plane.
This action will remove any transaction state from the packet core to return it to a known state.
This action will cause a service outage.

### [Deploy-AzMobileNetworkRollbackPacketCoreControlPlane](Deploy-AzMobileNetworkRollbackPacketCoreControlPlane.md)
Roll back the specified packet core control plane to the previous version, \"rollbackVersion\".
Multiple consecutive rollbacks are not possible.
This action may cause a service outage.

### [Get-AzMobileNetwork](Get-AzMobileNetwork.md)
Gets information about the specified mobile network.

### [Get-AzMobileNetworkAttachedDataNetwork](Get-AzMobileNetworkAttachedDataNetwork.md)
Gets information about the specified attached data network.

### [Get-AzMobileNetworkDataNetwork](Get-AzMobileNetworkDataNetwork.md)
Gets information about the specified data network.

### [Get-AzMobileNetworkPacketCoreControlPlane](Get-AzMobileNetworkPacketCoreControlPlane.md)
Gets information about the specified packet core control plane.

### [Get-AzMobileNetworkPacketCoreControlPlaneVersion](Get-AzMobileNetworkPacketCoreControlPlaneVersion.md)
Gets information about the specified packet core control plane version.

### [Get-AzMobileNetworkPacketCoreDataPlane](Get-AzMobileNetworkPacketCoreDataPlane.md)
Gets information about the specified packet core data plane.

### [Get-AzMobileNetworkService](Get-AzMobileNetworkService.md)
Gets information about the specified service.

### [Get-AzMobileNetworkSim](Get-AzMobileNetworkSim.md)
Gets information about the specified SIM.

### [Get-AzMobileNetworkSimGroup](Get-AzMobileNetworkSimGroup.md)
Gets information about the specified SIM group.

### [Get-AzMobileNetworkSimPolicy](Get-AzMobileNetworkSimPolicy.md)
Gets information about the specified SIM policy.

### [Get-AzMobileNetworkSite](Get-AzMobileNetworkSite.md)
Gets information about the specified mobile network site.

### [Get-AzMobileNetworkSlice](Get-AzMobileNetworkSlice.md)
Gets information about the specified network slice.

### [New-AzMobileNetwork](New-AzMobileNetwork.md)
create a mobile network.

### [New-AzMobileNetworkAttachedDataNetwork](New-AzMobileNetworkAttachedDataNetwork.md)
create an attached data network.
Must be created in the same location as its parent packet core data plane.

### [New-AzMobileNetworkDataNetwork](New-AzMobileNetworkDataNetwork.md)
create a data network.
Must be created in the same location as its parent mobile network.

### [New-AzMobileNetworkDataNetworkConfigurationObject](New-AzMobileNetworkDataNetworkConfigurationObject.md)
Create an in-memory object for DataNetworkConfiguration.

### [New-AzMobileNetworkPacketCoreControlPlane](New-AzMobileNetworkPacketCoreControlPlane.md)
create a packet core control plane.

### [New-AzMobileNetworkPacketCoreDataPlane](New-AzMobileNetworkPacketCoreDataPlane.md)
create a packet core data plane.
Must be created in the same location as its parent packet core control plane.

### [New-AzMobileNetworkPccRuleConfigurationObject](New-AzMobileNetworkPccRuleConfigurationObject.md)
Create an in-memory object for PccRuleConfiguration.

### [New-AzMobileNetworkService](New-AzMobileNetworkService.md)
create a service.
Must be created in the same location as its parent mobile network.

### [New-AzMobileNetworkServiceDataFlowTemplateObject](New-AzMobileNetworkServiceDataFlowTemplateObject.md)
Create an in-memory object for ServiceDataFlowTemplate.

### [New-AzMobileNetworkServiceResourceIdObject](New-AzMobileNetworkServiceResourceIdObject.md)
Create an in-memory object for ServiceResourceId.

### [New-AzMobileNetworkSim](New-AzMobileNetworkSim.md)
create a SIM.

### [New-AzMobileNetworkSimGroup](New-AzMobileNetworkSimGroup.md)
create a SIM group.

### [New-AzMobileNetworkSimPolicy](New-AzMobileNetworkSimPolicy.md)
create a SIM policy.
Must be created in the same location as its parent mobile network.

### [New-AzMobileNetworkSimStaticIPPropertiesObject](New-AzMobileNetworkSimStaticIPPropertiesObject.md)
Create an in-memory object for SimStaticIPProperties.

### [New-AzMobileNetworkSite](New-AzMobileNetworkSite.md)
Creates or updates a mobile network site.
Must be created in the same location as its parent mobile network.

### [New-AzMobileNetworkSiteResourceIdObject](New-AzMobileNetworkSiteResourceIdObject.md)
Create an in-memory object for SiteResourceId.

### [New-AzMobileNetworkSlice](New-AzMobileNetworkSlice.md)
create a network slice.
Must be created in the same location as its parent mobile network.

### [New-AzMobileNetworkSliceConfigurationObject](New-AzMobileNetworkSliceConfigurationObject.md)
Create an in-memory object for SliceConfiguration.

### [Remove-AzMobileNetwork](Remove-AzMobileNetwork.md)
Deletes the specified mobile network.

### [Remove-AzMobileNetworkAttachedDataNetwork](Remove-AzMobileNetworkAttachedDataNetwork.md)
Deletes the specified attached data network.

### [Remove-AzMobileNetworkBulkSimDelete](Remove-AzMobileNetworkBulkSimDelete.md)
Bulk delete SIMs from a SIM group.

### [Remove-AzMobileNetworkDataNetwork](Remove-AzMobileNetworkDataNetwork.md)
Deletes the specified data network.

### [Remove-AzMobileNetworkPacketCoreControlPlane](Remove-AzMobileNetworkPacketCoreControlPlane.md)
Deletes the specified packet core control plane.

### [Remove-AzMobileNetworkPacketCoreDataPlane](Remove-AzMobileNetworkPacketCoreDataPlane.md)
Deletes the specified packet core data plane.

### [Remove-AzMobileNetworkService](Remove-AzMobileNetworkService.md)
Deletes the specified service.

### [Remove-AzMobileNetworkSim](Remove-AzMobileNetworkSim.md)
Deletes the specified SIM.

### [Remove-AzMobileNetworkSimGroup](Remove-AzMobileNetworkSimGroup.md)
Deletes the specified SIM group.

### [Remove-AzMobileNetworkSimPolicy](Remove-AzMobileNetworkSimPolicy.md)
Deletes the specified SIM policy.

### [Remove-AzMobileNetworkSite](Remove-AzMobileNetworkSite.md)
Deletes the specified mobile network site.
This will also delete any network functions that are a part of this site.

### [Remove-AzMobileNetworkSlice](Remove-AzMobileNetworkSlice.md)
Deletes the specified network slice.

### [Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage](Trace-AzMobileNetworkCollectPacketCoreControlPlaneDiagnosticPackage.md)
Collect a diagnostics package for the specified packet core control plane.
This action will upload the diagnostics to a storage account.

### [Update-AzMobileNetwork](Update-AzMobileNetwork.md)
update mobile network tags.

### [Update-AzMobileNetworkAttachedDataNetwork](Update-AzMobileNetworkAttachedDataNetwork.md)
update an attached data network.
Must be created in the same location as its parent packet core data plane.

### [Update-AzMobileNetworkBulkSimUpload](Update-AzMobileNetworkBulkSimUpload.md)
Bulk upload SIMs to a SIM group.

### [Update-AzMobileNetworkBulkSimUploadEncrypted](Update-AzMobileNetworkBulkSimUploadEncrypted.md)
Bulk upload SIMs in encrypted form to a SIM group.
The SIM credentials must be encrypted.

### [Update-AzMobileNetworkDataNetwork](Update-AzMobileNetworkDataNetwork.md)
update a data network.
Must be created in the same location as its parent mobile network.

### [Update-AzMobileNetworkPacketCoreControlPlane](Update-AzMobileNetworkPacketCoreControlPlane.md)
update a packet core control plane.

### [Update-AzMobileNetworkPacketCoreDataPlane](Update-AzMobileNetworkPacketCoreDataPlane.md)
update a packet core data plane.
Must be created in the same location as its parent packet core control plane.

### [Update-AzMobileNetworkService](Update-AzMobileNetworkService.md)
Updates service.

### [Update-AzMobileNetworkSim](Update-AzMobileNetworkSim.md)
update a SIM.

### [Update-AzMobileNetworkSimGroup](Update-AzMobileNetworkSimGroup.md)
update a SIM group.

### [Update-AzMobileNetworkSimPolicy](Update-AzMobileNetworkSimPolicy.md)
update a SIM policy.
Must be created in the same location as its parent mobile network.

### [Update-AzMobileNetworkSite](Update-AzMobileNetworkSite.md)
update site tags.

### [Update-AzMobileNetworkSlice](Update-AzMobileNetworkSlice.md)
Updates slice.

