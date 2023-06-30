---
description: Learn about upcoming breaking changes to the Azure Az PowerShell module
ms.custom: devx-track-azurepowershell
ms.date: 06/09/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Upcoming breaking changes in Azure PowerShell
---

# Upcoming breaking changes in Azure PowerShell

## Az.Aks

### `New-AzAksCluster`

- The `-DockerBridgeCidr` parameter will be deprecated in Az 11.0.0 without being replaced.

## Az.Compute

### `New-AzDisk`

- Cmdlet breaking-change will happen to all parameter set
  - Starting in November 2023 the "New-AzDisk" cmdlet will deploy with the Trusted Launch configuration by default. This includes defaulting the "HyperVGeneration" parameter to "v2". To know more about Trusted Launch, please visit [learn.microsoft.com/azure/virtual-machines/trusted-launch](/azure/virtual-machines/trusted-launch)

### `New-AzVM`

- Cmdlet breaking-change will happen to all parameter set
  - Consider using the image alias including the version of the distribution you want to use in the "-Image" parameter of the "New-AzVM" cmdlet. On April 30, 2023, the image deployed using `UbuntuLTS` will reach its end of life. In October 2023, the aliases `UbuntuLTS`, `CentOS`, `Debian`, and `RHEL` will be removed.
  - Starting in November 2023 the "New-AzVM" cmdlet will deploy with the Trusted Launch configuration by default. To know more about Trusted Launch, please visit [docs.microsoft.com/azure/virtual-machines/trusted-launch](/azure/virtual-machines/trusted-launch)
  - It is recommended to use parameter "-PublicIpSku Standard" in order to create a new VM with a Standard public IP.Specifying zone(s) using the "-Zone" parameter will also result in a Standard public IP.If "-Zone" and "-PublicIpSku" are not specified, the VM will be created with a Basic public IP instead.Please note that the Standard SKU IPs will become the default behavior for VM creation in the future

### `New-AzVmss`

- Cmdlet breaking-change will happen to all parameter set
  - Starting November 2023, the "New-AzVmss" cmdlet will default to Trusted Launch VMSS. For more info, visit [aka.ms/trustedLaunchVMSS](https://aka.ms/trustedLaunchVMSS).
  - Starting November 2023, the "New-AzVmss" cmdlet will use new defaults: Flexible orchestration mode and enable NATv2 configuration for Load Balancer. To learn more about Flexible Orchestration modes, visit [aka.ms/orchestrationModeVMSS](https://aka.ms/orchestrationModeVMSS).
  - Consider using the image alias including the version of the distribution you want to use in the "-ImageName" parameter of the "New-AzVmss" cmdlet. On April 30, 2023, the image deployed using `UbuntuLTS` will reach its end of life. In November 2023, the aliases `UbuntuLTS`, `CentOS`, `Debian`, and `RHEL` will be removed.

## Az.DesktopVirtualization

### `New-AzWvdScalingPlan`

- Parameter breaking-change will happen to all parameter sets
  - `-HostPoolType`
    - The parameter : 'HostPoolType' is changing.
    - The change is expected to take effect from the version : '4.0.0'

## Az.PowerBIEmbedded

### `Get-AzPowerBIWorkspace`

- Cmdlet breaking-change will happen to all parameter set
  - The cmdlet is being deprecated. There will be no replacement for it.

### `Get-AzPowerBIWorkspaceCollection`

- Cmdlet breaking-change will happen to all parameter set
  - The cmdlet is being deprecated. There will be no replacement for it.

### `Get-AzPowerBIWorkspaceCollectionAccessKey`

- Cmdlet breaking-change will happen to all parameter set
  - The cmdlet is being deprecated. There will be no replacement for it.

### `New-AzPowerBIWorkspaceCollection`

- Cmdlet breaking-change will happen to all parameter set
  - The cmdlet is being deprecated. There will be no replacement for it.

### `Remove-AzPowerBIWorkspaceCollection`

- Cmdlet breaking-change will happen to all parameter set
  - The cmdlet is being deprecated. There will be no replacement for it.

### `Reset-AzPowerBIWorkspaceCollectionAccessKey`

- Cmdlet breaking-change will happen to all parameter set
  - The cmdlet is being deprecated. There will be no replacement for it.

## Az.Storage

### `New-AzStorageAccount`

- Cmdlet breaking-change will happen to all parameter set
  - Default value of AllowBlobPublicAccess will be changed from True to False in a future release. When AllowBlobPublicAccess is False on a storage account, it is not permitted to configure container ACLs to allow anonymous access to blobs within the storage account.

- Parameter breaking-change will happen to all parameter sets
  - `-EnableLargeFileShare`
    - EnableLargeFileShare parameter will be deprecated in a future release.

### `Set-AzStorageAccount`

- Parameter breaking-change will happen to all parameter sets
  - `-EnableLargeFileShare`
    - EnableLargeFileShare parameter will be deprecated in a future release.
