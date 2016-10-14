---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
online version: .\Get-AzureOperationalInsightsStorageInsight.md
schema: 2.0.0
---

# Set-AzureOperationalInsightsStorageInsight

## SYNOPSIS
Modifies an Operational Insights storage insight.

## SYNTAX

### ByWorkspaceName (Default)
```
Set-AzureOperationalInsightsStorageInsight [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-Name] <String> [[-StorageAccountKey] <String>] [[-Tables] <String[]>] [[-Containers] <String[]>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByWorkspaceObject
```
Set-AzureOperationalInsightsStorageInsight [-Workspace] <PSWorkspace> [-Name] <String>
 [[-StorageAccountKey] <String>] [[-Tables] <String[]>] [[-Containers] <String[]>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureOperationalInsightsStorageInsight** cmdlet modifies the configuration of an existing Operational Insights storage insight.

## EXAMPLES

### Example 1: Modify a storage insight by name
```
PS C:\>Set-AzureOperationalInsightsStorageInsight -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "MyWorkspace" -Name "MyStorageInsight" -Tables @("WADWindowsEventLogsTable")
```

This command modifies the tables that the storage insight named MyStorageInsight reads from.

### Example 2: Modify a storage insight by using a workspace object
```
PS C:\>$Workspace = Get-AzureOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace"
PS C:\> Set-AzureOperationalInsightsStorageInsight -Workspace $Workspace -Name "MyStorageInsight" -Containers @("wad-iis-logfiles")
```

The first command uses the Get-AzureOperationalInsightsWorkspace cmdlet to get the workspace named MyWorkspace, and then stores it in the $Workspace variable.

The second command modifies the containers that the storage insight named MyStorageInsight reads from.

## PARAMETERS

### -ResourceGroupName
Specifies the name of the Azure resource group that contains the storage insight to modify.

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
Specifies the name of a workspace.

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
Specifies the name of the storage insight to modify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountKey
Specifies the access key for the storage account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tables
Specifies an array of tables from which data is consumed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Containers
Specifies an array of containers from which the storage insight consumes data.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
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
Specifies the workspace that contains the storage insight to modify.

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

[Get-AzureOperationalInsightsStorageInsight](.\Get-AzureOperationalInsightsStorageInsight.md)

[Get-AzureOperationalInsightsWorkspace](.\Get-AzureOperationalInsightsWorkspace.md)

[New-AzureOperationalInsightsStorageInsight](.\New-AzureOperationalInsightsStorageInsight.md)

[Remove-AzureOperationalInsightsStorageInsight](.\Remove-AzureOperationalInsightsStorageInsight.md)

