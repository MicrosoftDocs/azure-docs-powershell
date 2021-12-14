---
external help file:
Module Name: Azs.ContainerRegistry.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerregistry.admin/get-azscontainerregistry
schema: 2.0.0
---

# Get-AzsContainerRegistry

## SYNOPSIS
Returns a list of container registries present in all tenant location.

## SYNTAX

```
Get-AzsContainerRegistry [-Location <String>] [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Returns a list of container registries present in all tenant location.

## EXAMPLES

### Example 1: Get List Azs Container Registries
```powershell
PS C:\> Get-AzsContainerRegistry | ConvertTo-Json

{
    "CreationDate":  "\/Date(1629160842681)\/",
    "Id":  "/subscriptions/7e41090c-4aa7-40bc-856a-a993f8fbd215/providers/Microsoft.ContainerRegistry.Admin/locations/redmond/registries/testregistry01",
    "Location":  "redmond",
    "Name":  "redmond/testregistry01",
    "PropertiesName":  "testregistry01",
    "RegistryId":  "/subscriptions/72b77b1b-3e43-4d00-8b5b-be6beceb7f3a/resourceGroups/acrtenanttestrg/providers/Microsoft.ContainerRegistry/registries/testregistry01",
    "RegistrySizeInByte":  3011,
    "ResourceGroup":  "acrtenanttestrg",
    "SubscriptionId":  "72b77b1b-3e43-4d00-8b5b-be6beceb7f3a",
    "Type":  "Microsoft.ContainerRegistry.Admin/locations/registries"
}
```

Returns a list of container registries present in all tenant location.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
The name of Azure region.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistry

## NOTES

ALIASES

## RELATED LINKS

