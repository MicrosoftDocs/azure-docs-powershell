---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
Module Name: AzureRM.Insights
ms.assetid: 6140E973-D7AB-4A28-A4FA-818E08129372
online version:
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Remove-AzureRmAutoscaleSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Remove-AzureRmAutoscaleSetting.md
---

# Remove-AzureRmAutoscaleSetting

## SYNOPSIS
Removes an Autoscale setting.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmAutoscaleSetting -ResourceGroup <String> -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmAutoscaleSetting** cmdlet removes an Autoscale setting.
You must specify the name of the setting and the name of the resource group to which it is assigned.

## EXAMPLES

## PARAMETERS

### -Name
Specifies the name of the Autoscale setting to remove.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Specifies the name of the resource group.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.AzureOperationResponse

## NOTES

## RELATED LINKS

[Add-AzureRmAutoscaleSetting](./Add-AzureRmAutoscaleSetting.md)

[Get-AzureRmAutoscaleSetting](./Get-AzureRmAutoscaleSetting.md)


