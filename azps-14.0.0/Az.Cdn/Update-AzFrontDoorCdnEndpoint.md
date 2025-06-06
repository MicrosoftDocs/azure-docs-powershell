---
external help file: Az.Cdn-help.xml
Module Name: Az.Cdn
online version: https://learn.microsoft.com/powershell/module/az.cdn/update-azfrontdoorcdnendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Update-AzFrontDoorCdnEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Update-AzFrontDoorCdnEndpoint.md
---

# Update-AzFrontDoorCdnEndpoint

## SYNOPSIS
update an existing AzureFrontDoor endpoint with the specified endpoint name under the specified subscription, resource group and profile.
Only tags can be updated after creating an endpoint.
To update origins, use the update Origin operation.
To update origin groups, use the update Origin group operation.
To update domains, use the update Custom Domain operation.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzFrontDoorCdnEndpoint -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-EnabledState <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateViaJsonString
```
Update-AzFrontDoorCdnEndpoint -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] -JsonString <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateViaJsonFilePath
```
Update-AzFrontDoorCdnEndpoint -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] -JsonFilePath <String> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateViaIdentityProfileExpanded
```
Update-AzFrontDoorCdnEndpoint -EndpointName <String> -ProfileInputObject <ICdnIdentity>
 [-EnabledState <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateViaIdentityProfile
```
Update-AzFrontDoorCdnEndpoint -EndpointName <String> -ProfileInputObject <ICdnIdentity>
 -EndpointUpdateProperty <IAfdEndpointUpdateParameters> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzFrontDoorCdnEndpoint -InputObject <ICdnIdentity> [-EnabledState <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
update an existing AzureFrontDoor endpoint with the specified endpoint name under the specified subscription, resource group and profile.
Only tags can be updated after creating an endpoint.
To update origins, use the update Origin operation.
To update origin groups, use the update Origin group operation.
To update domains, use the update Custom Domain operation.

## EXAMPLES

### Example 1: Update an AzureFrontDoor endpoint under the profile
```powershell
Update-AzFrontDoorCdnEndpoint -ResourceGroupName testps-rg-da16jm -ProfileName fdp-v542q6 -EndpointName end001 -EnabledState Disabled
```

```output
Location Name   ResourceGroupName
-------- ----   -----------------
Global   end001 testps-rg-da16jm
```

Update an AzureFrontDoor endpoint under the profile

### Example 2: Update an AzureFrontDoor endpoint under the profile via identity
```powershell
Get-AzFrontDoorCdnEndpoint  -ResourceGroupName testps-rg-da16jm -ProfileName fdp-v542q6 -EndpointName end011 | Update-AzFrontDoorCdnEndpoint -EnabledState Disabled
```

```output
Location Name   ResourceGroupName
-------- ----   -----------------
Global   end011 testps-rg-da16jm
```

Update an AzureFrontDoor endpoint under the profile via identity

## PARAMETERS

### -AsJob
Run the command as a job

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The DefaultProfile parameter is not functional.
Use the SubscriptionId parameter when available if executing the cmdlet against a different subscription.

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

### -EnabledState
Whether to enable use of this rule.
Permitted values are 'Enabled' or 'Disabled'

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaIdentityProfileExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointName
Name of the endpoint under the profile which is unique globally.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaJsonString, UpdateViaJsonFilePath, UpdateViaIdentityProfileExpanded, UpdateViaIdentityProfile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointUpdateProperty
Properties required to create or update an endpoint.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.IAfdEndpointUpdateParameters
Parameter Sets: UpdateViaIdentityProfile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JsonFilePath
Path of Json file supplied to the Update operation

```yaml
Type: System.String
Parameter Sets: UpdateViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Json string supplied to the Update operation

```yaml
Type: System.String
Parameter Sets: UpdateViaJsonString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Run the command asynchronously

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileInputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: UpdateViaIdentityProfileExpanded, UpdateViaIdentityProfile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProfileName
Name of the Azure Front Door Standard or Azure Front Door Premium which is unique within the resource group.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaJsonString, UpdateViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the Resource group within the Azure subscription.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaJsonString, UpdateViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Azure Subscription ID.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaJsonString, UpdateViaJsonFilePath
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Endpoint tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateExpanded, UpdateViaIdentityProfileExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.IAfdEndpointUpdateParameters

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.IAfdEndpoint

## NOTES

## RELATED LINKS
