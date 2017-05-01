---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmWebApp

## SYNOPSIS
Gets a web app.

## SYNTAX

### S1
```
Get-AzureRmWebApp [[-ResourceGroupName] <String>] [[-Name] <String>] [<CommonParameters>]
```

### S2
```
Get-AzureRmWebApp [-AppServicePlan] <ServerFarmWithRichSku> [<CommonParameters>]
```

### S3
```
Get-AzureRmWebApp [-Location] <String> [<CommonParameters>]
```

## DESCRIPTION
The Get-AzureRmWebApp cmdlet gets an Azure web app in the specified resource group.

## EXAMPLES

### --------------------------  Example 1: Get a web app  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmWebApp -Name "MyWebApp" -ResourceGroupName "Default-Web-WestUS" -SlotName "dev"
```

This command gets web app named MyWebApp for the slot named dev in the resource group named Default-Web-WestUS.

## PARAMETERS

### -AppServicePlan
@{Text=}

```yaml
Type: ServerFarmWithRichSku
Parameter Sets: S2
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
@{Text=}

```yaml
Type: String
Parameter Sets: S3
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the web app to get.

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group that contains the web app.

```yaml
Type: String
Parameter Sets: S1
Aliases: 

Required: False
Position: 0
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

[New-AzureRMWebApp]()

[Remove-AzureRMWebApp]()

[Restart-AzureRMWebApp]()

[Start-AzureRMWebApp]()

[Stop-AzureRMWebApp]()

