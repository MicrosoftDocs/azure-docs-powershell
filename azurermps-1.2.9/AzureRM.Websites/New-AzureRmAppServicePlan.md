---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRmAppServicePlan

## SYNOPSIS
Creates an Azure App Service plan.

## SYNTAX

### S1
```
New-AzureRmAppServicePlan [-Location] <String> [[-Tier] <String>] [[-NumberofWorkers] <Int32>]
 [[-WorkerSize] <String>] [[-AseName] <String>] [[-AseResourceGroupName] <String>]
 [-ResourceGroupName] <String> [-Name] <String> [<CommonParameters>]
```

### S2
```
New-AzureRmAppServicePlan [-Location] <String> [[-Tier] <String>] [[-NumberofWorkers] <Int32>]
 [[-WorkerSize] <String>] [[-AseName] <String>] [[-AseResourceGroupName] <String>]
 [-AppServicePlan] <ServerFarmWithRichSku> [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmAppServicePlan** cmdlet creates an Azure App Service plan in the specified geographical location with the specified tier, worker size, and number of workers.

## EXAMPLES

### Example 1: Create an App Service plan
```
PS C:\> New-AzureRmAppServicePlan -ResourceGroupName "Default-Web-WestUS" -Name "MyServicePlan" -Location "West US" -Tier "Basic" -NumberofWorkers 2 -WorkerSize "Small"
```

This command creates an App Service plan named "MyServicePlan" in the geographical location "West US" with a basic tier.

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

### -AseName
Specifies the name of the App Service environment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AseResourceGroupName
Specifies the name of the resource group for the App Service environment.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the geographical location of the App Service plan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the App Service plan.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that will contain the new App Service plan.

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
Parameter Sets: (All)
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
Parameter Sets: (All)
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

[Get-AzureRmAppServicePlan](./Get-AzureRmAppServicePlan.md)

[Remove-AzureRmAppServicePlan](./Remove-AzureRmAppServicePlan.md)

[Set-AzureRmAppServicePlan](./Set-AzureRmAppServicePlan.md)
