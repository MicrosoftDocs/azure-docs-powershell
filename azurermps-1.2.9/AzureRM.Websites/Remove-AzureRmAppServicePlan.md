---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-AzureRmAppServicePlan

## SYNOPSIS
Removes an Azure App Service plan.

## SYNTAX

### S1
```
Remove-AzureRmAppServicePlan [-Force] [-ResourceGroupName] <String> [-Name] <String> [<CommonParameters>]
```

### S2
```
Remove-AzureRmAppServicePlan [-Force] [-AppServicePlan] <ServerFarmWithRichSku> [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmAppServicePlan** cmdlet removes an Azure App Service plan.

## EXAMPLES

### Example 1: Remove an App Service plan
```
PS C:\> Remove-AzureRmAppServicePlan -ResourceGroupName "Default-Web-WestUS" -Name "MyAppServicePlan"
```

This command removes the Azure App Service plan named "MyAppServicePlan" in the resource group named "Default-Web-WestUS".

## PARAMETERS

### -AppServicePlan
Specifies an object that contains details about the App Service plan.

```yaml
Type: ServerFarmWithRichSku
Parameter Sets: S2
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Indicates whether to forcefully remove the App Service plan without confirmation.

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

### -Name
Specifies the name of the App Service plan to remove.

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the App Service plan to remove.

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.WebSites.Models.ServerFarmWithRichSku

## OUTPUTS

### Microsoft.Azure.AzureOperationResponse

## NOTES

## RELATED LINKS

[Get-AzureRmAppServicePlan](./Get-AzureRmAppServicePlan.md)

[New-AzureRmAppServicePlan](./New-AzureRmAppServicePlan.md)

[Set-AzureRmAppServicePlan](./Set-AzureRmAppServicePlan.md)
