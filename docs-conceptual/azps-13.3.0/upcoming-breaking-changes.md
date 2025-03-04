---
description: Learn about upcoming breaking changes to the Az PowerShell module
ms.custom: devx-track-azurepowershell
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Upcoming breaking changes in Azure PowerShell
---

# Upcoming breaking changes in Azure PowerShell

The breaking changes listed in this article are planned for the next major release of the Az
PowerShell module unless otherwise noted. Per our
[Support lifecycle](azureps-support-lifecycle.md), breaking changes in Azure PowerShell occur twice
a year with major versions of the Az PowerShell module.

## Az.Accounts

### `Get-AzAccessToken`

- Cmdlet breaking-change will happen to all parameter sets
  - The Token property of the output type will be changed from String to SecureString. Add the [-AsSecureString] switch to avoid the impact of this upcoming breaking change.
  - This change is expected to take effect from Az.Accounts version: 5.0.0 and Az version: 14.0.0

## Az.Blueprint

### `Export-AzBlueprintWithArtifact`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Get-AzBlueprint`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Get-AzBlueprintArtifact`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Get-AzBlueprintAssignment`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Import-AzBlueprintWithArtifact`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `New-AzBlueprint`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `New-AzBlueprintArtifact`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `New-AzBlueprintAssignment`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Publish-AzBlueprint`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Remove-AzBlueprintAssignment`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Set-AzBlueprint`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Set-AzBlueprintArtifact`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

### `Set-AzBlueprintAssignment`

- Cmdlet breaking-change will happen to all parameter sets
  - Blueprints and associated cmdlets will be deprecated as early as July 2026. Customers are encouraged to transition to Template Specs and Deployments Stacks to support their scenarios beyond that date. Migration documentation is available at [Migrate blueprints to deployment stacks](/azure/azure-resource-manager/bicep/migrate-blueprint).
  - This change is expected to take effect from Az.Blueprint version: - and Az version: 16.0.0

## Az.ContainerInstance

### `New-AzContainerGroup`

- Parameter breaking-change will happen to all parameter sets
  - `-OSType`
    - The parameter : 'OSType' is changing.
    - This change will take effect on '5/21/2025'- The change is expected to take effect from Az version : '14.0.0'
    - The change is expected to take effect from version : '5.0.0'

### `New-AzContainerInstanceContainerGroupProfile`

- Parameter breaking-change will happen to all parameter sets
  - `-OSType`
    - The parameter : 'OSType' is changing.
    - Change description : Removing the default value of OSType parameter. 
    - This change will take effect on '5/21/2025'- The change is expected to take effect from Az version : '14.0.0'
    - The change is expected to take effect from version : '5.0.0'
