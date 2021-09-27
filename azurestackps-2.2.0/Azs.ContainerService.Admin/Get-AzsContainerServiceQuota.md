---
external help file:
Module Name: Azs.ContainerService.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerservice.admin/get-azscontainerservicequota
schema: 2.0.0
---

# Get-AzsContainerServiceQuota

## SYNOPSIS
Returns a list of container service quotas at the given location.

## SYNTAX

```
Get-AzsContainerServiceQuota [-Location <String>] [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Returns a list of container service quotas at the given location.

## EXAMPLES

### Example 1: Get Quota for Container Service
```powershell
PS C:\> Get-AzsContainerServiceQuota -Location "redmond" | ConvertTo-Json
{
  "Id": "/subscriptions/f9712d12-aa4d-4d37-8f46-fabf3c07c836/providers/Microsoft.ContainerService.Admin/locations/redmond/quotas/Unlimited",
  "Name": "redmond/Unlimited",
  "PropertiesName": "Unlimited",
  "Type": "Microsoft.ContainerService.Admin/locations/quotas"
}
```

Returns a quota for container service.

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerServiceAdmin.Models.Api20191101.IContainerServiceQuotaListValueItem

## NOTES

ALIASES

## RELATED LINKS

