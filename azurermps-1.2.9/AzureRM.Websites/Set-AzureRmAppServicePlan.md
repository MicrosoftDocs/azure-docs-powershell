---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRmAppServicePlan

## SYNOPSIS
Modifies an Azure App Service plan.

## SYNTAX

### S1
```
Set-AzureRmAppServicePlan [[-AdminSiteName] <String>] [[-Tier] <String>] [[-NumberofWorkers] <Int32>]
 [[-WorkerSize] <String>] [-ResourceGroupName] <String> [-Name] <String> [<CommonParameters>]
```

### S2
```
Set-AzureRmAppServicePlan [-AppServicePlan] <ServerFarmWithRichSku> [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRmAppServicePlan** cmdlet modifes an Azure App Service plan.

## EXAMPLES

### Example 1: Modify the scaling of an App Service plan
```
PS C:\> Set-AzureRmAppServicePlan -ResourceGroupName "Default-Web-WestUS" -Name "ContosoASP" -NumberofWorkers 15
```

This command modifies the number of workers allowed for the App Service plan named "ContosoASP" that belongs to the resource group named "Default-Web-WestUS".

## PARAMETERS

### -AdminSiteName
Specifies the name of the administration site for the App Service plan.

```yaml
Type: String
Parameter Sets: S1
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppServicePlan
Specifies an object that contains updated details about the App Service plan.

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

### -Name
Specifies the name of the App Service plan to modify.

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

### -NumberofWorkers
Specifies the number of workers to allow in the App Service plan.

```yaml
Type: Int32
Parameter Sets: S1
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the App Service plan to modify.

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

### -Tier
Specifies the pricing tier. The valid values are: Free, Shared, Basic, Standard, and Premium.
The default is Free.

```yaml
Type: String
Parameter Sets: S1
Aliases:
Accepted values: Free, Shared, Basic, Standard, Premium

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkerSize
Specifies the size of the worker pool.
Valid values are: Small, Medium, and Large.

```yaml
Type: String
Parameter Sets: S1
Aliases:
Accepted values: Small, Medium, Large, ExtraLarge

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.WebSites.Models.ServerFarmWithRichSku

## OUTPUTS

### Microsoft.Azure.Management.WebSites.Models.ServerFarmWithRichSku

## NOTES

## RELATED LINKS

[Get-AzureRMAppServicePlan](./Get-AzureRMAppServicePlan.md)

[New-AzureRMAppServicePlan](./New-AzureRMAppServicePlan.md)

[Remove-AzureRMAppServicePlan](./Remove-AzureRMAppServicePlan.md)
