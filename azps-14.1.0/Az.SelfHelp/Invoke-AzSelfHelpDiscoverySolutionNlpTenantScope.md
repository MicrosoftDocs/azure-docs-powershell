---
external help file: Az.SelfHelp-help.xml
Module Name: Az.SelfHelp
online version: https://learn.microsoft.com/powershell/module/az.selfhelp/invoke-azselfhelpdiscoverysolutionnlptenantscope
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SelfHelp/SelfHelp/help/Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SelfHelp/SelfHelp/help/Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope.md
---

# Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope

## SYNOPSIS
Solution discovery using natural language processing.

## SYNTAX

### PostExpanded (Default)
```
Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope [-AdditionalContext <String>] [-IssueSummary <String>]
 [-ResourceId <String>] [-ServiceId <String>] [-DefaultProfile <PSObject>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Post
```
Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope -DiscoverSolutionRequest <IDiscoveryNlpRequest>
 [-DefaultProfile <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PostViaJsonFilePath
```
Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope -JsonFilePath <String> [-DefaultProfile <PSObject>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PostViaJsonString
```
Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope -JsonString <String> [-DefaultProfile <PSObject>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Solution discovery using natural language processing.

## EXAMPLES

### Example 1: Discover Solution using natural language at tenant scope
```powershell
Invoke-AzSelfHelpDiscoverySolutionNlpTenantScope -IssueSummary "Billing Issues"
```

```output
[No output]
```

Search for relevant Azure Diagnostics, Solutions and Troubleshooters using a natural language issue summary.

## PARAMETERS

### -AdditionalContext
Additional information in the form of a string.

```yaml
Type: System.String
Parameter Sets: PostExpanded
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

### -DiscoverSolutionRequest
Discover NLP request.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.SelfHelp.Models.IDiscoveryNlpRequest
Parameter Sets: Post
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IssueSummary
Describe the issue with the affected resource.

```yaml
Type: System.String
Parameter Sets: PostExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonFilePath
Path of Json file supplied to the Post operation

```yaml
Type: System.String
Parameter Sets: PostViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Json string supplied to the Post operation

```yaml
Type: System.String
Parameter Sets: PostViaJsonString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Provide resourceId of affected resource

```yaml
Type: System.String
Parameter Sets: PostExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceId
Service Classification id for the resource.
You can find required serviceId from Services API: https://learn.microsoft.com/rest/api/support/services/list?tabs=HTTP Service Id is the GUID which can be found under name field in Services List response

```yaml
Type: System.String
Parameter Sets: PostExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.SelfHelp.Models.IDiscoveryNlpRequest

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.SelfHelp.Models.IDiscoveryNlpResponse

## NOTES

## RELATED LINKS
