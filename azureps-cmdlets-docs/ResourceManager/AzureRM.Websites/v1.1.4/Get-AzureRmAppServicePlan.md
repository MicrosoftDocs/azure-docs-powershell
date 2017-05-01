---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmAppServicePlan

## SYNOPSIS
Gets an App Service plan.

## SYNTAX

### S1
```
Get-AzureRmAppServicePlan [[-ResourceGroupName] <String>] [[-Name] <String>] [<CommonParameters>]
```

### S2
```
Get-AzureRmAppServicePlan [-Location] <String> [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureRmAppServicePlan cmdlet gets an Azure App Service plan in the specified resource group.

## EXAMPLES

### --------------------------  Example 1: Get an App Service plan  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmAppServicePlan -Name "MyServicePlan" -ResourceGroupName "Default-Web-WestUS"
```

This command gets the App Service plan named MyServicePlan in the resource group named Default-Web-WestUS.

## PARAMETERS

### -Location
@{Text=}

```yaml
Type: String
Parameter Sets: S2
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the App Service plan to get.

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the App Service plan to get.

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureRMAppServicePlan]()

[Remove-AzureRMAppServicePlan]()

[Set-AzureRMAppServicePlan]()

