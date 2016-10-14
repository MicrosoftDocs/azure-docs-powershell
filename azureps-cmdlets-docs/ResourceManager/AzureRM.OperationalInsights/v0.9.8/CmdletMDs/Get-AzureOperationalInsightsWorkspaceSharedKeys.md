---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
online version: .\Get-AzureOperationalInsightsWorkspace.md
schema: 2.0.0
---

# Get-AzureOperationalInsightsWorkspaceSharedKeys

## SYNOPSIS
Gets the shared keys for an Operational Insights workspace.

## SYNTAX

```
Get-AzureOperationalInsightsWorkspaceSharedKeys [-ResourceGroupName] <String> [-Name] <String>
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureOperationalInsightsWorkspaceSharedKeys** cmdlet lists the shared keys for an Operational Insights workspace.
The keys are used to connect Operational Insights agents to the workspace.

## EXAMPLES

### Example 1: Get shared keys by workspace name
```
PS C:\>Get-AzureOperationalInsightsWorkspaceSharedKeys -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace"
```

This command gets the shared keys for the workspace named Myworkspace in the resource group named ContosoResourceGroup.

### Example 2: Get shared keys by using the pipeline
```
PS C:\>Get-AzureOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace" | Get-AzureOperationalInsightsWorkspaceSharedKeys
```

This command gets the workspace named MyWorkspace using the Get-AzureOperationalInsightsWorkspace cmdlet, and then passes the workspace to the **Get-AzureOperationalInsightsWorkspaceSharedKeys** cmdlet.
The command gets the shared keys for that workspace.

## PARAMETERS

### -ResourceGroupName
Specifies the name of the Azure resource group that contains the shared keys to get.

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
Specifies the name of an Operational Insights workspace.
This cmdlet gets the shared keys for the workspace that this parameter specifies.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

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

[Get-AzureOperationalInsightsWorkspace](.\Get-AzureOperationalInsightsWorkspace.md)

