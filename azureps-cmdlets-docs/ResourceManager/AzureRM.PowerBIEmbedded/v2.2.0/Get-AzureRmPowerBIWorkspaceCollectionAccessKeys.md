---
external help file: Microsoft.Azure.Commands.Management.PowerBIEmbedded.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F6ED8A3A-AD65-4B48-A73E-F43447640D6B
---

# Get-AzureRmPowerBIWorkspaceCollectionAccessKeys

## SYNOPSIS
Gets the current access keys associated with a Power BI workspace collection.

## SYNTAX

```
Get-AzureRmPowerBIWorkspaceCollectionAccessKeys [-ResourceGroupName] <String>
 [-WorkspaceCollectionName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmPowerBIWorkspaceCollectionAccessKeys** cmdlet gets the current access keys associated with a Power BI workspace collection.

## EXAMPLES

### Example 1: Get access keys
```
PS C:\>Get-AzureRmPowerBIWorkspaceCollectionAccessKeys -ResourceGroupName "ResourceGroup17" -WorkspaceCollectionName "WCN11"
```

This command gets access keys for the workspace collection named WCN11 in the specified resource group.

## PARAMETERS

### -ResourceGroupName
Specifies the name of the resource group of the collection.

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

### -WorkspaceCollectionName
Specifies the name of the Power BI workspace collection on which this cmdlet operates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name, ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Reset-AzureRmPowerBIWorkspaceCollectionAccessKeys](./Reset-AzureRmPowerBIWorkspaceCollectionAccessKeys.md)


