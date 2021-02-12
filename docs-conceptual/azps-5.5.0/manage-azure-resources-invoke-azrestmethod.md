---
title: Manage Azure resources with Invoke-AzRestMethod
description: How to use Azure PowerShell to manage resources with the Invoke-AzRestMethod cmdlet.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/24/2020 
ms.custom: devx-track-azurepowershell 
ms.service: azure-powershell
---

# Manage Azure resources with Invoke-AzRestMethod

[Invoke-AzRestMethod](/powershell/module/az.accounts/invoke-azrestmethod) is an Azure PowerShell
cmdlet that was introduced in Az PowerShell module version 4.4.0. It allows you to make custom HTTP
requests to the Azure Resource Management (ARM) endpoint using the Az context.

This cmdlet is useful when you want to manage Azure services for features that aren't yet available
in the Az PowerShell module.

## How to use Invoke-AzRestMethod

As an example, you can allow access to Azure Container Registry (ACR) only for specific networks or
deny public access. As of Az PowerShell module version 4.5.0, that feature isn't available yet in
the [Az.ContainerRegistry PowerShell module](/powershell/module/Az.ContainerRegistry/). However, it
can be managed in the interim with `Invoke-AzRestMethod`.

## Using Invoke-AzRestMethod with GET operations

The following example demonstrates how to use the `Invoke-AzRestMethod` cmdlet with a GET operation:

```azurepowershell-interactive
$getParams = @{
  ResourceGroupName = 'myresourcegroup'
  ResourceProviderName = 'Microsoft.ContainerRegistry'
  ResourceType = 'registries'
  Name = 'myacr'
  ApiVersion = '2019-12-01-preview'
  Method = 'GET'
}
Invoke-AzRestMethod @getParams
```

To allow maximum flexibility, most of the parameters for `Invoke-AzRestMethod` are optional.
However, when you're managing resources within a resource group, you'll most likely need to provide
either the full ID to the resource or parameters like resource group, resource provider, and
resource type.

The `ResourceType` and `Name` parameters can take multiple values when targeting resources that
require more than one name. For example, to manipulate a saved search in a Log Analytics workspace,
the parameters look like the following example:
`-ResourceType @('workspaces', 'savedsearches') -Name @('my-la', 'my-search')`.

Using a mapping based on the position in the array, the cmdlet constructs the following resource:
`Id:'/workspaces/my-la/savedsearches/my-search'`.

The `APIVersion` parameter allows you to use a specific API version, including preview ones. The
supported API versions for Azure Resource providers can be found in the
[azure-rest-api-specs](https://github.com/Azure/azure-rest-api-specs) GitHub repository.

You can find the definition for the 2019-12-01-preview version of ACR in the following location:
[azure-rest-api-specs/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/](https://github.com/Azure/azure-rest-api-specs/tree/master/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview).

## Using Invoke-AzRestMethod with PATCH operations

You can disable public access to the existing ACR named `myacr` in the `myresourcegroup` resource
group using the `Invoke-AzRestMethod` cmdlet.

To disable the public network access, you need to make a **PATCH** call to the API that changes the
value of the `publicNetwokAccess` parameter as shown in the following example:

```azurepowershell-interactive
$patchParams = @{
  ResourceGroupName = 'myresourcegroup'
  Name = 'myacr'
  ResourceProviderName = 'Microsoft.ContainerRegistry'
  ResourceType = 'registries'
  ApiVersion = '2019-12-01-preview'
  Payload = '{ "properties": {
     "publicNetworkAccess": "Disabled"
     } }'
  Method = 'PATCH'
}
Invoke-AzRestMethod @patchParams
```

The `Payload` property is a JSON string that shows the path of the property to be modified.

All the parameters for this API are described in the **rest-api-spec** file associated with this API.
The specific definition for the publicNetworkAccess parameter can be found in the
[container registry JSON file](https://github.com/Azure/azure-rest-api-specs/blob/2a9da9a79d0a7b74089567ec4f0289f3e0f31bec/specification/containerregistry/resource-manager/Microsoft.ContainerRegistry/preview/2019-12-01-preview/containerregistry.json)
for the 2019-12-01 preview version of the API.

To only allow access to the registry from a specific IP address, the payload needs to be modified as
shown in the following example:

```azurepowershell-interactive
$specificIpParams = @{
  ResourceGroupName = 'myresourcegroup'
  Name = 'myacr'
  ResourceProviderName = 'Microsoft.ContainerRegistry'
  ResourceType = 'registries'
  ApiVersion = '2019-12-01-preview'
  Payload = '{ "properties": {
      "networkRuleSet": {
      "defaultAction": "Deny",
      "ipRules": [ {
         "action": "Allow",
         "value": "24.22.123.123"
         } ]
      }
  } }'
  -Method = 'PATCH'
}
Invoke-AzRestMethod @specificIpParams
```

## Comparison to Get-AzResource, New-AzResource, and Remove-AzResource

The `*-AzResource` cmdlets allow you to customize the REST API call to Azure by specifying the
resource type, the API version, and the properties to be updated. However, the properties need to be
created first as a `PSObject`. This process adds an additional level of complexity and can easily
become complicated.

`Invoke-AzRestMethod` offers a simple way to manage Azure resources. As shown in the previous
example, you can build a JSON string and use it to customize the REST API call without having to
precreate any `PSObjects`.

If you're already familiar with the `*-AzResource` cmdlets, you can continue using them. We have no
plans to stop supporting them. With `Invoke-AzRestMethod`, we have added a new cmdlet to your toolkit.

## See Also

* [Get-AzResource](/powershell/module/az.resources/get-azresource)
* [New-AzResource](/powershell/module/az.resources/new-azresource)
* [Remove-AzResource](/powershell/module/az.resources/remove-azresource)
