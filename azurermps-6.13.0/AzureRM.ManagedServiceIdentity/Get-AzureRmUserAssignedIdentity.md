---
external help file: Microsoft.Azure.Commands.ManagedServiceIdentity.dll-Help.xml
Module Name: AzureRM.ManagedServiceIdentity
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.managedserviceidentity/get-azurermuserassignedidentity
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ManagedServiceIdentity/Commands.ManagedServiceIdentity/help/Get-AzureRmUserAssignedIdentity.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ManagedServiceIdentity/Commands.ManagedServiceIdentity/help/Get-AzureRmUserAssignedIdentity.md
---

# Get-AzureRmUserAssignedIdentity

## SYNOPSIS
Gets User Assigned Identity/identities.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SuscriptionParameterSet (Default)
```
Get-AzureRmUserAssignedIdentity [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroupParameterSet
```
Get-AzureRmUserAssignedIdentity -ResourceGroupName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmUserAssignedIdentity** gets existing user assigned identities.

## EXAMPLES

### Example 1
This example cmdlet gets the User Assigned Identity with name **ID1** under the resource group **PSRG**

```powershell
PS C:\> Get-AzureRmUserAssignedIdentity -ResourceGroupName PSRG -Name ID1

Id                : /subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1

ResourceGroupName : PSRG

Name              : ID1

Location          : westus

TenantId          : 00001111-aaaa-2222-bbbb-3333cccc4444

PrincipalId       : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientId          : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientSecretUrl   : https://control-westus.identity.azure.net/subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1/credentials?tid=00001111-aaaa-2222-bbbb-3333cccc4444&oid=00001111-aaaa-2222-bbbb-3333cccc4444&aid=00001111-aaaa-2222-bbbb-3333cccc4444

Type              : Microsoft.ManagedIdentity/userAssignedIdentities
```

### Example 2
This example cmdlet gets all the User Assigned Identities under the resource group **PSRG**

```powershell
PS C:\> Get-AzureRmUserAssignedIdentity -ResourceGroupName PSRG

Id                : /subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1

ResourceGroupName : PSRG

Name              : ID1

Location          : westus

TenantId          : 00001111-aaaa-2222-bbbb-3333cccc4444

PrincipalId       : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientId          : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientSecretUrl   : https://control-westus.identity.azure.net/subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1/credentials?tid=00001111-aaaa-2222-bbbb-3333cccc4444&oid=00001111-aaaa-2222-bbbb-3333cccc4444&aid=00001111-aaaa-2222-bbbb-3333cccc4444

Type              : Microsoft.ManagedIdentity/userAssignedIdentities


Id                : /subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID2

ResourceGroupName : PSRG

Name              : ID2

Location          : westus

TenantId          : 00001111-aaaa-2222-bbbb-3333cccc4444

PrincipalId       : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientId          : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientSecretUrl   : https://control-westus.identity.azure.net/subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID2/credentials?tid=00001111-aaaa-2222-bbbb-3333cccc4444&oid=00001111-aaaa-2222-bbbb-3333cccc4444&aid=00001111-aaaa-2222-bbbb-3333cccc4444

Type              : Microsoft.ManagedIdentity/userAssignedIdentities
```

### Example 3
This example cmdlet gets all the User Assigned Identities under the subscription.

```powershell
PS C:\> Get-AzureRmUserAssignedIdentity

Id                : /subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1

ResourceGroupName : PSRG

Name              : ID1

Location          : westus

TenantId          : 00001111-aaaa-2222-bbbb-3333cccc4444

PrincipalId       : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientId          : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientSecretUrl   : https://control-westus.identity.azure.net/subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1/credentials?tid=00001111-aaaa-2222-bbbb-3333cccc4444&oid=00001111-aaaa-2222-bbbb-3333cccc4444&aid=00001111-aaaa-2222-bbbb-3333cccc4444

Type              : Microsoft.ManagedIdentity/userAssignedIdentities


Id                : /subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID2

ResourceGroupName : PSRG

Name              : ID2

Location          : westus

TenantId          : 00001111-aaaa-2222-bbbb-3333cccc4444

PrincipalId       : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientId          : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientSecretUrl   : https://control-westus.identity.azure.net/subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID2/credentials?tid=00001111-aaaa-2222-bbbb-3333cccc4444&oid=00001111-aaaa-2222-bbbb-3333cccc4444&aid=00001111-aaaa-2222-bbbb-3333cccc4444

Type              : Microsoft.ManagedIdentity/userAssignedIdentities


Id                : /subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG2/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1

ResourceGroupName : PSRG2

Name              : ID1

Location          : westus

TenantId          : 00001111-aaaa-2222-bbbb-3333cccc4444

PrincipalId       : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientId          : 00001111-aaaa-2222-bbbb-3333cccc4444

ClientSecretUrl   : https://control-westus.identity.azure.net/subscriptions/586d0246-0344-49dc-a790-59c916b0c309/resourcegroups/PSRG2/providers/Microsoft.ManagedIdentity/userAssignedIdentities/ID1/credentials?tid=00001111-aaaa-2222-bbbb-3333cccc4444&oid=00001111-aaaa-2222-bbbb-3333cccc4444&aid=00001111-aaaa-2222-bbbb-3333cccc4444

Type              : Microsoft.ManagedIdentity/userAssignedIdentities
```

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The Identity name.

```yaml
Type: System.String
Parameter Sets: ResourceGroupParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
The resource group name.

```yaml
Type: System.String
Parameter Sets: ResourceGroupParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ManagedServiceIdentity.Models.PsUserAssignedIdentity

## NOTES

## RELATED LINKS
