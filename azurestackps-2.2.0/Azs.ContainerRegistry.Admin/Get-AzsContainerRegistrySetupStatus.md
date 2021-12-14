---
external help file:
Module Name: Azs.ContainerRegistry.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerregistry.admin/get-azscontainerregistrysetupstatus
schema: 2.0.0
---

# Get-AzsContainerRegistrySetupStatus

## SYNOPSIS
Returns the status of the container registry setup.

## SYNTAX

### Get (Default)
```
Get-AzsContainerRegistrySetupStatus [-Location <String>] [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzsContainerRegistrySetupStatus -INPUTOBJECT \<IContainerRegistryAdminIdentity>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Returns the status of the container registry setup.

## EXAMPLES

### Example 1: Get Azs ContainerRegistry Setup Status
```powershell
PS C:\> (Get-AzsContainerRegistrySetupStatus).ToJsonString() 

{
  "id": "/subscriptions/7e41090c-4aa7-40bc-856a-a993f8fbd215/providers/Microsoft.ContainerRegistry.Setup/locations/redmond/setup/value",
  "name": "redmond/value",
  "type": "Microsoft.ContainerRegistry.Setup/locations/setup",
  "properties": {
    "status": "Completed"
  }
}
```

Returns the status of the container registry setup.

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

### -InputObject
Identity Parameter
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.IContainerRegistryAdminIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
The name of Azure region.

```yaml
Type: System.String
Parameter Sets: Get
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
Parameter Sets: Get
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.IContainerRegistryAdminIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.ISetupResult

## NOTES

ALIASES

COMPLEX PARAMETER PROPERTIES

To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.


INPUTOBJECT \<IContainerRegistryAdminIdentity>: Identity Parameter
  - `[CapacityName <String>]`: The name of the capacity parameter.
  - `[ConfigurationName <String>]`: The name of the configuration.
  - `[Id <String>]`: Resource identity path
  - `[Location <String>]`: The name of Azure region.
  - `[QuotaName <String>]`: The name of the container registry quota.
  - `[SubscriptionId <String>]`: The ID of the target subscription.

## RELATED LINKS

