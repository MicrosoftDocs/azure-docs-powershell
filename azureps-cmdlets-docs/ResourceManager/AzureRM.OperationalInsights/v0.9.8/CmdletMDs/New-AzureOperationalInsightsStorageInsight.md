---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
online version: .\Get-AzureOperationalInsightsStorageInsight.md
schema: 2.0.0
---

# New-AzureOperationalInsightsStorageInsight

## SYNOPSIS
Creates an Operational Insights storage insight.

## SYNTAX

### ByWorkspaceName (Default)
```
New-AzureOperationalInsightsStorageInsight [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-Name] <String> [-StorageAccountResourceId] <String> [-StorageAccountKey] <String> [[-Tables] <String[]>]
 [[-Containers] <String[]>] [-Force] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByWorkspaceObject
```
New-AzureOperationalInsightsStorageInsight [-Workspace] <PSWorkspace> [-Name] <String>
 [-StorageAccountResourceId] <String> [-StorageAccountKey] <String> [[-Tables] <String[]>]
 [[-Containers] <String[]>] [-Force] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureOperationalInsightsStorageInsight** cmdlet creates an Operational Insights storage insight in an existing workspace.

## EXAMPLES

### Example 1: Create a storage insight by name
```
PS C:\>$Storage = Get-AzureStorageAccount -ResourceGroupName "ContosoResourceGroup" -Name "ContosoStorage"
PS C:\> $StorageKey = ($Storage | Get-AzureStorageAccountKey).Key1
PS C:\> New-AzureOperationalInsightsStorageInsight -ResourceGroupName "ContosoResourceGroup" -WorkspaceName "MyWorkspace" -Name "MyStorageInsight" -StorageAccountResourceId $Storage.Id -StorageAccountKey $StorageKey -Tables @("WADWindowsEventLogsTable")
```

The first command uses the Get-AzureStorageAccount cmdlet to get the storage account named ContosoStorage, and then stores it in the $Storage variable.

The second command passes the storage account in $Storage to the Get-AzureStorageAccountKey cmdlet to get the specified storage account key, and then stores it in the $StorageKey variable.

The final command creates a storage insight named MyStorageInsight in the workspace named MyWorkspace.
This storage insight consumes data from the WADWindowsEventLogsTable table in the specified storage account resource.

### Example 2: Create a storage insight by using a workspace object
```
PS C:\>$Workspace = Get-AzureOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace"
PS C:\> $Storage = Get-AzureStorageAccount -ResourceGroupName "ContosoResourceGroup" -Name "ContosoStorage"
PS C:\> $StorageKey = ($Storage | Get-AzureStorageAccountKey).Key1
PS C:\> New-AzureOperationalInsightsStorageInsight -Workspace $Workspace -Name "MyStorageInsight" -StorageAccountResourceId $Storage.Id -StorageAccountKey $StorageKey -Tables @("WADWindowsEventLogsTable")
```

The first command uses the Get-AzureOperationalInsightsWorkspace cmdlet to get the workspace named MyWorkspace, and then stores it in the $Workspace variable.

The second command uses the **Get-AzureStorageAccount** cmdlet to get the specified storage account, and then stores it in the $Storage variable.

The third command passes the storage account in $Storage to the Get-AzureStorageAccountKey cmdlet to get the specified key, and then stores it in the $StorageKey variable.

The final command creates a storage insight named MyStorageInsight in the workspace defined in $Workspace.
The storage insight consumes data from the WADWindowsEventLogsTable table in the specified storage account resource.

## PARAMETERS

### -ResourceGroupName
Specifies the name of an Azure resource group that contains a workspace.

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
Specifies the name of an existing workspace.

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
Specifies the name of the storage insight to create.

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

### -StorageAccountResourceId
Specifies the Azure resource of a storage account.
You can use the Get-AzureStorageAccount cmdlet to get a storage account and access the ID property of the result.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
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

Required: True
Position: 5
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
Position: 6
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
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Specifies the workspace to contain the new storage insight.

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

[Remove-AzureOperationalInsightsStorageInsight](.\Remove-AzureOperationalInsightsStorageInsight.md)

[Set-AzureOperationalInsightsStorageInsight](.\Set-AzureOperationalInsightsStorageInsight.md)

