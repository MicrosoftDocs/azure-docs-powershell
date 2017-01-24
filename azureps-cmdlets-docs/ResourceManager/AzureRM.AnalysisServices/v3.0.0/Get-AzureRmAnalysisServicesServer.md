---
external help file: Microsoft.Azure.Commands.AnalysisServices.dll-help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmAnalysisServicesServer

## SYNOPSIS
Gets details of an Analysis Services server.

## SYNTAX

```
Get-AzureRmAnalysisServicesServer [[-ResourceGroupName] <String>] [[-Name] <String>]
```

## DESCRIPTION
The **Get-AzureRmAnalysisServicesServer** cmdlet gets details for a Microsoft SQL Server Analysis Services server.

## EXAMPLES

### Example 1: Get Analysis Services servers in a resource group 
```
PS C:\> Get-AzureRmAnalysisServicesServer -ResourceGroupName "ContosoResourceGroup"
```

This command gets all Analysis Services servers in the resource group named ContosoResourceGroup.

### Example 2: Get a server
```
PS C:\> Get-AzureRmAnalysisServicesServer -ResourceGroupName "ContosoResourceGroup" -Name "ContosoServer03"
```

This command gets an Analysis Services server named ContosoServer03 in the resource group named ContosoResourceGroup.

## PARAMETERS

### -Name
Specifies the name of an Analysis Services server.

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

### -ResourceGroupName
Specifies the name of the Azure resource group to which the Analysis Services server belongs.

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

## INPUTS

## OUTPUTS

## NOTES
Alias: **Get-AzureAs**

## RELATED LINKS

[New-AzureRmAnalysisServicesServer](./New-AzureRmAnalysisServicesServer.md)

[Remove-AzureRmAnalysisServicesServer](./Remove-AzureRmAnalysisServicesServer.md)

[Resume-AzureRmAnalysisServicesServer](./Resume-AzureRmAnalysisServicesServer.md)

[Set-AzureRmAnalysisServicesServer](./Set-AzureRmAnalysisServicesServer.md)

[Suspend-AzureRmAnalysisServicesServer](./Suspend-AzureRmAnalysisServicesServer.md)

[Test-AzureRmAnalysisServicesServer](./Test-AzureRmAnalysisServicesServer.md)