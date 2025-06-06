---
external help file: Az.SelfHelp-help.xml
Module Name: Az.SelfHelp
online version: https://learn.microsoft.com/powershell/module/az.selfhelp/invoke-azselfhelpwarmsolutionup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SelfHelp/SelfHelp/help/Invoke-AzSelfHelpWarmSolutionUp.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SelfHelp/SelfHelp/help/Invoke-AzSelfHelpWarmSolutionUp.md
---

# Invoke-AzSelfHelpWarmSolutionUp

## SYNOPSIS
Warm up the solution resource by preloading asynchronous diagnostics results into cache

## SYNTAX

### WarmExpanded (Default)
```
Invoke-AzSelfHelpWarmSolutionUp -Scope <String> -SolutionResourceName <String> [-Parameter <Hashtable>]
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### WarmViaJsonString
```
Invoke-AzSelfHelpWarmSolutionUp -Scope <String> -SolutionResourceName <String> -JsonString <String>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### WarmViaJsonFilePath
```
Invoke-AzSelfHelpWarmSolutionUp -Scope <String> -SolutionResourceName <String> -JsonFilePath <String>
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Warm
```
Invoke-AzSelfHelpWarmSolutionUp -Scope <String> -SolutionResourceName <String>
 -SolutionWarmUpRequestBody <ISolutionWarmUpRequestBody> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WarmViaIdentityExpanded
```
Invoke-AzSelfHelpWarmSolutionUp -InputObject <ISelfHelpIdentity> [-Parameter <Hashtable>]
 [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### WarmViaIdentity
```
Invoke-AzSelfHelpWarmSolutionUp -InputObject <ISelfHelpIdentity>
 -SolutionWarmUpRequestBody <ISolutionWarmUpRequestBody> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Warm up the solution resource by preloading asynchronous diagnostics results into cache

## EXAMPLES

### Example 1: Warm up the solution resource
```powershell
$resourceName = "sampleRName"
$parameters = [ordered]@{ 
    "ProductId" = "13491"
}
Invoke-AzSelfHelpWarmSolutionUp -Scope "/subscriptions/6bded6d5-a6af-43e1-96d3-bf71f6f5f8ba/resourceGroups/aits-data-inestion/providers/Microsoft.KeyVault/vaults/kv-akshayko519290291381" -SolutionResourceName $resourceName -Parameter $parameters
```

```output
[No output]
```

Warm up the solution resource by preloading asynchronous diagnostics results into cache

## PARAMETERS

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

### -InputObject
Identity Parameter

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.SelfHelp.Models.ISelfHelpIdentity
Parameter Sets: WarmViaIdentityExpanded, WarmViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JsonFilePath
Path of Json file supplied to the Warm operation

```yaml
Type: System.String
Parameter Sets: WarmViaJsonFilePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JsonString
Json string supplied to the Warm operation

```yaml
Type: System.String
Parameter Sets: WarmViaJsonString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter
Dictionary of \<string\>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: WarmExpanded, WarmViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns true when the command succeeds

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

### -Scope
scope = resourceUri of affected resource.\<br/\> For example: /subscriptions/0d0fcd2e-c4fd-4349-8497-200edb3923c6/resourcegroups/myresourceGroup/providers/Microsoft.KeyVault/vaults/test-keyvault-non-read

```yaml
Type: System.String
Parameter Sets: WarmExpanded, WarmViaJsonString, WarmViaJsonFilePath, Warm
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SolutionResourceName
Solution resource Name.

```yaml
Type: System.String
Parameter Sets: WarmExpanded, WarmViaJsonString, WarmViaJsonFilePath, Warm
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SolutionWarmUpRequestBody
Solution WarmUpRequest body

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.SelfHelp.Models.ISolutionWarmUpRequestBody
Parameter Sets: Warm, WarmViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.PowerShell.Cmdlets.SelfHelp.Models.ISelfHelpIdentity

### Microsoft.Azure.PowerShell.Cmdlets.SelfHelp.Models.ISolutionWarmUpRequestBody

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
