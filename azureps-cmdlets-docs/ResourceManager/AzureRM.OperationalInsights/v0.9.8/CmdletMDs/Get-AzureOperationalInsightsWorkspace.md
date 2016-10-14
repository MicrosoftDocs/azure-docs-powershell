---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
online version: .\New-AzureOperationalInsightsWorkspace.md
schema: 2.0.0
---

# Get-AzureOperationalInsightsWorkspace

## SYNOPSIS
Gets an Operational Insights workspace.

## SYNTAX

```
Get-AzureOperationalInsightsWorkspace [[-ResourceGroupName] <String>] [[-Name] <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureOperationalInsightsWorkspace** cmdlet gets an existing Operational Insights workspace.
Specify the *Name* parameter to get a workspace by its name.
If you do not specify the *Name* parameter, this cmdlet gets all of the workspaces in a specified resource group.
If you do not specify a name and a resource group, this cmdlet gets all of the workspaces in the subscription.

## EXAMPLES

### Example 1: Get a workspace by name
```
PS C:\>Get-AzureOperationalInsightsWorkspace -Name "MyWorkspace" -ResourceGroupName "ContosoResourceGroup"
```

This command gets a workspace named MyWorkspace in the resource group named ContosoResourceGroup.

## PARAMETERS

### -ResourceGroupName
Specifies the name of the Azure resource group that contains the workspace to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the workspace to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

[New-AzureOperationalInsightsWorkspace](.\New-AzureOperationalInsightsWorkspace.md)

[Remove-AzureOperationalInsightsWorkspace](.\Remove-AzureOperationalInsightsWorkspace.md)

[Set-AzureOperationalInsightsWorkspace](.\Set-AzureOperationalInsightsWorkspace.md)

