---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
ms.assetid: E3D7A3FE-40D4-4495-BA39-493F85F304AD
online version: https://learn.microsoft.com/powershell/module/az.operationalinsights/new-azoperationalinsightsapplicationinsightsdatasource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/New-AzOperationalInsightsApplicationInsightsDataSource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/New-AzOperationalInsightsApplicationInsightsDataSource.md
---

# New-AzOperationalInsightsApplicationInsightsDataSource

## SYNOPSIS
Collect logs from given Application-Insights application.

## SYNTAX

### ByWorkspaceName (Default)
```
New-AzOperationalInsightsApplicationInsightsDataSource [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByWorkspaceObjectByApplicationParameters
```
New-AzOperationalInsightsApplicationInsightsDataSource [-Workspace] <PSWorkspace>
 -ApplicationSubscriptionId <String> -ApplicationResourceGroupName <String> -ApplicationName <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByWorkspaceObjectByApplicationResourceId
```
New-AzOperationalInsightsApplicationInsightsDataSource [-Workspace] <PSWorkspace>
 -ApplicationResourceId <String> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByWorkspaceNameByApplicationParameters
```
New-AzOperationalInsightsApplicationInsightsDataSource [-ResourceGroupName] <String> [-WorkspaceName] <String>
 -ApplicationSubscriptionId <String> -ApplicationResourceGroupName <String> -ApplicationName <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByWorkspaceNameByApplicationResourceId
```
New-AzOperationalInsightsApplicationInsightsDataSource [-ResourceGroupName] <String> [-WorkspaceName] <String>
 -ApplicationResourceId <String> [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-AzOperationalInsightsApplicationInsightsDataSource** cmdlet enables the collection of logs from a given Application-Insights application.

## EXAMPLES

### Example 1: Create application-insights data source in workspace
```powershell
New-AzOperationalInsightsApplicationInsightsDataSource -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "MyWorkspace" -ApplicationSubscriptionId "a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1" -ApplicationResourceGroupName "ContosoResourceGroup" -ApplicationName "MyAIApplication"
```

```output
Name              : subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/ContosoResourceGroup/providers/microsoft.insights/components/MyAIApplication
ResourceGroupName : ContosoResourceGroup
WorkspaceName     : MyWorkspace
ResourceId        : /subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/ContosoResourceGroup/providers/Microsoft.OperationalInsights/workspaces/MyWorkspace/datasources/subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/ContosoResourceGroup/providers/microsoft.insights/components/MyAIApplication
Kind              : ApplicationInsights
Properties        : {"linkedResourceId":"subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/ContosoResourceGroup/providers/microsoft.insights/components/MyAIApplication","status":"Succeeded"}
```

This command creates an application-insights data source of a given application in a given log analytics workspace. This enables the collection of logs from given application to the log analytics workspace.

### Example 2: Get workspace object and create application-insights data source by the application resource id
```powershell
Get-AzOperationalInsightsWorkspace -Name "MyWorkspace" -ResourceGroupName "ContosoResourceGroup" | New-AzOperationalInsightsApplicationInsightsDataSource -ApplicationResourceId "/subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/ContosoResourceGroup/providers/microsoft.insights/components/MyAIApplication"
```

```output
Name              : subscriptions/b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2/resourceGroups/ContosoResourceGroup/providers/microsoft.insights/components/MyAIApplication
ResourceGroupName : ContosoResourceGroup
WorkspaceName     : MyWorkspace
ResourceId        : /subscriptions/b1b1b1b1-cccc-dddd-eeee-f2f2f2f2f2f2/resourceGroups/ContosoResourceGroup/providers/Microsoft.OperationalInsights/workspaces/MyWorkspace/datasources/subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/ContosoResourceGroup/providers/microsoft.insights/components/MyAIApplication
Kind              : ApplicationInsights
Properties        : {"linkedResourceId":"subscriptions/a0a0a0a0-bbbb-cccc-dddd-e1e1e1e1e1e1/resourceGroups/ContosoResourceGroup/providers/microsoft.insights/components/MyAIApplication","status":"Succeeded"}
```

This command demonstrates getting a log analytics workspace object and then passing the output to create an associated application-insights data source by the application resource id. 

## PARAMETERS

### -ApplicationName
The name of the linked application.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceObjectByApplicationParameters, ByWorkspaceNameByApplicationParameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationResourceGroupName
The resource group name of the linked application.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceObjectByApplicationParameters, ByWorkspaceNameByApplicationParameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationResourceId
The linked application resource id.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceObjectByApplicationResourceId, ByWorkspaceNameByApplicationResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationSubscriptionId
The subscription id of the linked application.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceObjectByApplicationParameters, ByWorkspaceNameByApplicationParameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Don't ask for confirmation.

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
Parameter Sets: ByWorkspaceNameByApplicationParameters, ByWorkspaceNameByApplicationResourceId
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Workspace
The workspace that will contain the data source.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter Sets: ByWorkspaceObjectByApplicationParameters, ByWorkspaceObjectByApplicationResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkspaceName
The name of the workspace that will contain the data source.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceNameByApplicationParameters, ByWorkspaceNameByApplicationResourceId
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataSource

## NOTES

## RELATED LINKS
