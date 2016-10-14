---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
online version: .\Get-AzureOperationalInsightsWorkspace.md
schema: 2.0.0
---

# Get-AzureOperationalInsightsStorageInsight

## SYNOPSIS
Gets Operational Insights storage insights.

## SYNTAX

### ByWorkspaceName (Default)
```
Get-AzureOperationalInsightsStorageInsight [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [[-Name] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByWorkspaceObject
```
Get-AzureOperationalInsightsStorageInsight [-Workspace] <PSWorkspace> [[-Name] <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureOperationalInsightsStorageInsight** cmdlet gets Operational Insights storage insights.
Specify the *Name* parameter to get a storage insight by its name.
If you do not specify the *Name* parameter, this cmdlet gets all of the storage insights in a workspace.

## EXAMPLES

### Example 1: Get a storage insight by name
```
PS C:\>Get-AzureOperationalInsightsStorageInsight -Name "MyStorageInsight" -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "ContosoWorkspace"
```

This command gets the storage insight named MyStorageInsight from the workspace named ContosoWorkspace.

### 1: Get a storage insight by using a workspace object
```
PS C:\>$Workspace = Get-AzureOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace"
PS C:\> Get-AzureOperationalInsightsStorageInsight -Workspace $Workspace -Name "MyStorageInsight"
```

The first command uses the Get-AzureOperationalInsightsWorkspace cmdlet to get an Operational Insights workspace, and then stores it in the $Workspace variable.

The second command gets the storage insight named MyStorageInsight for the workspace in $Workspace.

## PARAMETERS

### -ResourceGroupName
Specifies the name of an Azure resource group that contains the storage insight to get.

```yaml
Type: String
Parameter Sets: ByWorkspaceName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceName
Specifies the name of the workspace that contains the storage insight to get.

```yaml
Type: String
Parameter Sets: ByWorkspaceName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage insight to get.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### -Workspace
Specifies the **Workspace** object that contains the storage insight to get.

```yaml
Type: PSWorkspace
Parameter Sets: ByWorkspaceObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureOperationalInsightsWorkspace](.\Get-AzureOperationalInsightsWorkspace.md)

[New-AzureOperationalInsightsStorageInsight](.\New-AzureOperationalInsightsStorageInsight.md)

[Remove-AzureOperationalInsightsStorageInsight](.\Remove-AzureOperationalInsightsStorageInsight.md)

[Set-AzureOperationalInsightsStorageInsight](.\Set-AzureOperationalInsightsStorageInsight.md)

