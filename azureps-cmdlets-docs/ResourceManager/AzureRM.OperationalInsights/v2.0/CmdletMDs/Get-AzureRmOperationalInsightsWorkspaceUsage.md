---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
online version: 3a46bcd5-ad81-411a-92aa-7788ebd2473e
schema: 2.0.0
---

# Get-AzureRmOperationalInsightsWorkspaceUsage

## SYNOPSIS
Gets the usage data for a workspace.

## SYNTAX

```
Get-AzureRmOperationalInsightsWorkspaceUsage [-ResourceGroupName] <String> [-Name] <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmOperationalInsightsWorkspaceUsage** cmdlet retrieves the usage data for a workspace.
This exposes how much data has been analyzed by the workspace over a certain period.

## EXAMPLES

### Example 1: Get usage data by workspace name
```
PS C:\>Get-AzureRmOperationalInsightsWorkspaceUsage  ¢â‚¬"ResourceGroupName "ContosoResourceGroup"  ¢â‚¬"Name "MyWorkspace"
```

This command gets the usage details for the workspace named MyWorkspace in the specified resource group.

### Example 2: Get usage data using the pipeline
```
PS C:\>Get-AzureRmOperationalInsightsWorkspace  ¢â‚¬"ResourceGroupName "ContosoResourceGroup"  ¢â‚¬"Name "MyWorkspace" | Get-AzureOperationalInsightsWorkspaceUsage
```

This command gets the workspace named MyWorkSpace using the Get-AzureRmOperationalInsightsWorkspace cmdlet, and then passes the workspace to the current cmdlet.
The command gets the usage details for that workspace.

## PARAMETERS

### -ResourceGroupName
Specifies the name of an Azure resource group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the workspace name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Azure Operational Insights Cmdlets](.\AzureRM.OperationalInsights.md)

[Get-AzureRmOperationalInsightsWorkspace](.\Get-AzureRmOperationalInsightsWorkspace.md)

