---
title: Azure PowerShell Change Log | Microsoft Docs
description: This is a history of changes made to Azure PowerShell in the latest release.
services: azure
author: sdwheeler
manager: carmonm
ms.assetid: e2dec06a-4179-49e3-b6b1-b0f278956d11
ms.service:
ms.product: azure
ms.devlang: powershell
ms.topic: reference
ms.workload:
ms.date: 03/22/2017
ms.author: sewhee
---

# Release notes

This is a history of changes made to Azure PowerShell in the latest release. For a comprehensive
history of changes, see the [Change log](https://github.com/Azure/azure-powershell/blob/dev/ChangeLog.md)
on GitHub.

## 2017.03.09 - Version 3.7.0
* ApiManagement
    * Added new cmdlets to manage Backend entity
        - New-AzureRmApiManagementBackend
        - Get-AzureRmApiManagementBackend
        - Set-AzureRmApiManagementBackend
        - Remove-AzureRmApiManagementBackend
    * Created supporting cmdlets to create in-memory objects required while Creating or Updating Backend entity
        - New-AzureRmApiManagementBackendCredential
        - New-AzureRmApiManagementBackendProxy
* Billing
    * New Cmdlet Get-AzureRmBillingInvoice
        - cmdlet to retrieve azure billing invoices of the subscription.
* Compute
    * Updated Set-AzureRmVMAEMExtension and Test-AzureRmVMAEMExtension cmdlets to support managed disks
* LogicApp
    * New cmdlets for X12 Interchange Control Number disaster recovery:
        - Get-AzureRmIntegrationAccountGeneratedIcn
        - Get-AzureRmIntegrationAccountReceivedIcn
        - Remove-AzureRmIntegrationAccountReceivedIcn
        - Set-AzureRmIntegrationAccountGeneratedIcn
        - Set-AzureRmIntegrationAccountReceivedIcn
* Network
    * Added support for connection draining to Application Gateways
        - Added Get-AzureRmApplicationGatewayConnectionDraining
        - Added New-AzureRmApplicationGatewayConnectionDraining
        - Added Remove-AzureRmApplicationGatewayConnectionDraining
        - Added Set-AzureRmApplicationGatewayConnectionDraining
        - Updated Add-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining
        - Updated New-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining
        - Updated Set-AzureRmApplicationGatewayBackendHttpSettings: Added optional parameter -ConnectionDraining

    * Remapped unused 'Name' parameter in ExpressRoute cmdlets to 'ExpressRouteCircuitName'
        - Get-AzureRmExpressRouteCircuitARPTable
        - Get-AzureRmExpressRouteCircuitRouteTable
        - Get-AzureRmExpressRouteCircuitRouteTableSummary
        - Get-AzureRmExpressRouteCircuitStats
* Sql
    * Bug fix - Auditing and Threat Detection cmdlets now return a meaningfully error instead of null reference error.
    * Updating Transparent Data Encryption (TDE) with Bring Your Own Key (BYOK) support cmdlets for updated API.
* Websites
    * Update help documentation for AppServicePlan cmdlets
* ServiceManagement
    * Update the output object of migration cmdlets (Move-AzureService, Move-AzureStorageAccount, Move-AzureVirtualNetwork, Move-AzureNetworkSecurityGroup, Move-AzureReservedIP, Move-AzureRouteTable):
        - ValidationMessages contain "Information" and "Warning" messages in addition to "Error" messages.
        - Result output is changed according to ValidationMessages.

    * Removed ManagedCache cmdlets.  These cmdlets were non-functional and have been deprecated for more than a year
        - Get-AzureManagedCacheLocation
        - Get-AzureManagedCache
        - Get-AzureManagedCacheAccessKey
        - Get-AzureManagedCacheNamedCache
        - New-AzureManagedCache
        - New-AzureManagedCacheAccessKey
        - New-AzureManagedCacheNamedCache
        - Remove-AzureManagedCache
        - Remove-AzureManagedCacheNamedCache
        - Set-AzureManagedCache
        - Set-AzureManagedCacheNamedCache
