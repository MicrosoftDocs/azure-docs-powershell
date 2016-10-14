---
external help file: Microsoft.Azure.Commands.OperationalInsights.dll-Help.xml
online version: .\Get-AzureOperationalInsightsWorkspace.md
schema: 2.0.0
---

# Set-AzureOperationalInsightsWorkspace

## SYNOPSIS
Modifies an Operational Insights workspace.

## SYNTAX

### ByName (Default)
```
Set-AzureOperationalInsightsWorkspace [-ResourceGroupName] <String> [-Name] <String> [[-Sku] <String>]
 [[-Tags] <Hashtable>] [-Profile <AzureProfile>] [<CommonParameters>]
```

### ByObject
```
Set-AzureOperationalInsightsWorkspace [-Workspace] <PSWorkspace> [[-Sku] <String>] [[-Tags] <Hashtable>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureOperationalInsightsWorkspace** cmdlet modifies the configuration of an existing Operational Insights workspace.

## EXAMPLES

### Example 1: Modify a workspace by name
```
PS C:\>Set-AzureOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace" -Sku Standard -Tags @{ "Department" = "IT" }
```

This command modifies the SKU and tags of the workspace named MyWorkspace in the resource group named ContosoResourceGroup.

### Example 2: Update a workspace by using the pipeline
```
PS C:\>Get-AzureOperationalInsightsWorkspace -ResourceGroupName "ContosoResourceGroup" -Name "MyWorkspace" | Set-AzureOperationalInsightsWorkspace -Sku "Premium"
```

This command uses the Get-AzureOperationalInsightsWorkspace cmdlet to get the workspace named MyWorkSpace, and then passes it to the current cmdlet to set the SKU to Premium.

## PARAMETERS

### -ResourceGroupName
Specifies the name of the Azure resource group that contains the workspace to modify.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the workspace to modify.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sku
Specifies the service tier of the workspace.
The acceptable values for this parameter are:

- Free
- Standard 
- Premium

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

### -Tags
Specifies the resource tags for the workspace.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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
Specifies the workspace to modify.

```yaml
Type: PSWorkspace
Parameter Sets: ByObject
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

[New-AzureOperationalInsightsWorkspace](.\New-AzureOperationalInsightsWorkspace.md)

[Remove-AzureOperationalInsightsWorkspace](.\Remove-AzureOperationalInsightsWorkspace.md)

