---
external help file: Microsoft.Azure.Commands.AnalysisServices.dll-Help.xml
online version: 
schema: 2.0.0
---

# Test-AzureRmAnalysisServicesServer

## SYNOPSIS
Tests whether an Analysis Services server exists.

## SYNTAX

```
Test-AzureRmAnalysisServicesServer [-Name] <String> [[-ResourceGroupName] <String>]
```

## DESCRIPTION
The **Test-AzureRmAnalysisServicesServer** cmdlet tests whether a Microsoft SQL Server Analysis Services server exists.

## EXAMPLES

### Example 1: Test for an Analysis Services server 
```
PS C:\> Test-AzureRmAnalysisServicesServer -Name "ContosoServer03" -ResourceGroupName "ContosoResourceGroup"
```

This command test whether there is an Analysis Services server named ContosoServer03 in ContosoResourceGroup.

## PARAMETERS

### -Name
Specifies the name of an Analysis Services server.

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

### -ResourceGroupName
Specifies the name of the Azure resource group to which the Analysis Services server belongs.

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

## INPUTS

## OUTPUTS

### System.Boolean

## NOTES
Alias: **Test-AzureAs**

## RELATED LINKS

[Get-AzureRmAnalysisServicesServer](./Get-AzureRmAnalysisServicesServer.md)

[New-AzureRmAnalysisServicesServer](./New-AzureRmAnalysisServicesServer.md)

[Remove-AzureRmAnalysisServicesServer](./Remove-AzureRmAnalysisServicesServer.md)

[Resume-AzureRmAnalysisServicesServer](./Resume-AzureRmAnalysisServicesServer.md)

[Set-AzureRmAnalysisServicesServer](./Set-AzureRmAnalysisServicesServer.md)

[Suspend-AzureRmAnalysisServicesServer](./Suspend-AzureRmAnalysisServicesServer.md)
