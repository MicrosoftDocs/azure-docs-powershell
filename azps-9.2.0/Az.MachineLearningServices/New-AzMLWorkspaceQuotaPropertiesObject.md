---
external help file: 
Module Name: Az.MachineLearningServices
online version: https://docs.microsoft.com/powershell/module/az.MLWorkspace/new-AzMLWorkspaceQuotaPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/New-AzMLWorkspaceQuotaPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/New-AzMLWorkspaceQuotaPropertiesObject.md
---

# New-AzMLWorkspaceQuotaPropertiesObject

## SYNOPSIS
Create an in-memory object for QuotaBaseProperties.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.machinelearningservices/new-azmlworkspacequotapropertiesobject) for up-to-date information.

## SYNTAX

```
New-AzMLWorkspaceQuotaPropertiesObject [-Id <String>] [-Limit <Int64>] [-Type <String>] [-Unit <QuotaUnit>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for QuotaBaseProperties.

## EXAMPLES

### Example 1: Create an in-memory object for QuotaBaseProperties pass it to as value of Value parameter of  Update-AzMLServiceQuota
```powershell
New-AzMLWorkspaceQuotaPropertiesObject
```

Create an in-memory object for QuotaBaseProperties

## PARAMETERS

### -Id
Specifies the resource ID.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Limit
The maximum permitted quota of the resource.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the resource type.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unit
An enum describing the unit of quota measurement.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Support.QuotaUnit
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Models.Api20220501.QuotaBaseProperties

## NOTES

ALIASES

## RELATED LINKS
