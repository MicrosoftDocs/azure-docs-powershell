---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/remove-aznetworkmanagerverifierworkspacereachabilityanalysisintent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent.md
---

# Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent

## SYNOPSIS
To remove network manager verifier workspace reachability analysis intent. 

## SYNTAX

### ByName (Default)
```
Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent -Name <String> -NetworkManagerName <String>
 -ResourceGroupName <String> -VerifierWorkspaceName <String> [-Force] [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByInputObject
```
Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent -InputObject <PSReachabilityAnalysisIntent>
 [-Force] [-PassThru] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceId
```
Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent -ResourceId <String> [-Force] [-PassThru]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent** cmdlet removes a given Verifier Workspace Reachability Analysis Intent

## EXAMPLES

### Example 1
```powershell
Remove-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent -Name "ameIntent2" -NetworkManagerName "TestNM" -ResourceGroupName "TestRG" -VerifierWorkspaceName "AmeWorkspace"
```

```output
Confirm
Are you sure you want to remove resource 'ameIntent2'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

Removed the Verifier Workspace Reachability Analysis Intent named 'ameIntent2'.

## PARAMETERS

### -AsJob
Run cmdlet in the background

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
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Do not ask for confirmation.

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

### -InputObject
The Verifier Workspace Analysis Intent.


```yaml
Type: Microsoft.Azure.Commands.Network.Models.NetworkManager.PSReachabilityAnalysisIntent
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
The resource name.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkManagerName
The network manager name.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
{{ Fill PassThru Description }}

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

### -ResourceGroupName
The resource group name.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
The resource id.


```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VerifierWorkspaceName
The verifier workspace name.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent](./Get-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent.md)

[New-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent](./New-AzNetworkManagerVerifierWorkspaceReachabilityAnalysisIntent.md)
