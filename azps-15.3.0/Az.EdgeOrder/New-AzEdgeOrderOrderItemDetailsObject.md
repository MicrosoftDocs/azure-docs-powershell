---
external help file: Az.EdgeOrder-help.xml
Module Name: Az.EdgeOrder
online version: https://learn.microsoft.com/powershell/module/Az.EdgeOrder/new-azedgeorderorderitemdetailsobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/EdgeOrder/help/New-AzEdgeOrderOrderItemDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/EdgeOrder/help/New-AzEdgeOrderOrderItemDetailsObject.md
cmdletStatusMessage: This cmdlet is part of a **Preview** module. Preview versions aren't recommended for use in production environments. For more information, see https://aka.ms/azps-refstatus.
cmdletStatus: preview
---
# New-AzEdgeOrderOrderItemDetailsObject

## SYNOPSIS
Create an in-memory object for OrderItemDetails.

## SYNTAX

```
New-AzEdgeOrderOrderItemDetailsObject -OrderItemType <String> -ProductDetail <IProductDetails>
 [-NotificationEmailList <String[]>] [-Preference <IPreferences>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for OrderItemDetails.

## EXAMPLES

### Example 1: Creates orderItemDetails object.
```powershell
$HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
$details = New-AzEdgeOrderOrderItemDetailsObject -OrderItemType "Purchase"  -ProductDetail  @{"HierarchyInformation"=$HierarchyInformation}
```

Create an in-memory object for OrderItemDetails.

## PARAMETERS

### -NotificationEmailList
Additional notification email list.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrderItemType
Order item type.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Preference
Customer notification Preferences.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.IPreferences
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductDetail
Unique identifier for configuration.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.IProductDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.OrderItemDetails

## NOTES

## RELATED LINKS

