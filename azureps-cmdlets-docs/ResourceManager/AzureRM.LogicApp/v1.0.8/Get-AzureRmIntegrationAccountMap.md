---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmIntegrationAccountMap

## SYNOPSIS
Gets the specified integration account map from the Azure resource group.

## SYNTAX

```
Get-AzureRmIntegrationAccountMap [-ResourceGroupName <String>] [-Name <String>] [-MapName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmIntegrationAccountMap cmdlet retrieves integration account map from the Azure resource group and returns an object that represents the integration account map.
Use this cmdlet to get the integration account map from specified resource group.
You can get the integration account map by specifying the integration account name, resource group name and map name.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get the integration account map by name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountMap -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -MapName "IntegrationAccountMap1"
```

Id                   : /subscriptions/\<SubscriptionId\>/resourceGroups/ResourceGroup1/providers/Microsoft.Logic/integrationAccounts/IntegrationAccount1/maps/IntegrationAccountMap1
Name                 : IntegrationAccountMap1
Type                 : Microsoft.Logic/integrationAccounts/maps
CreatedTime          : 3/24/2016 10:34:26 PM
ChangedTime          : 3/24/2016 10:34:26 PM
MapType              : Xslt
ContentType          : 
ContentLink          : https://\<baseurl\>/integrationaccounts8811f0155a364b5e9618ba28f7180601/99D1E_XSLT_INTEGRATIONACCOUNT
                       MAP1-9A960F9B71C844CDB09D4922B3BCFF61?sv=2014-02-14&sr=b&sig=\<value\>
ContentSize          : 3056
Metadata             :

### --------------------------  Example 2 : Get the integration account maps by integration account name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountMap -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1"
```

This commands gets the integration account maps by integration account name.

Id                   : /subscriptions/\<SubscriptionId\>/resourceGroups/ResourceGroup1/providers/Microsoft.Logic/integrationAccounts/IntegrationAccount1/maps/IntegrationAccountMap1
Name                 : IntegrationAccountMap1
Type                 : Microsoft.Logic/integrationAccounts/maps
CreatedTime          : 3/24/2016 10:34:26 PM
ChangedTime          : 3/24/2016 10:34:26 PM
MapType              : Xslt
ContentType          : 
ContentLink          : https://\<baseurl\>/integrationaccounts8811f0155a364b5e9618ba28f7180601/99D1E_XSLT_INTEGRATIONACCOUNT
                       MAP1-9A960F9B71C844CDB09D4922B3BCFF61?sv=2014-02-14&sr=b&sig=\<value\>
ContentSize          : 3056
Metadata             :

## PARAMETERS

### -InformationAction
@{Text=}

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MapName
Specifies a name for the integration account map.
This parameter is optional.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the integration account.
This parameter is required.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies a name for the resource group.
This parameter is required.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.IntegrationAccountMap

## NOTES

## RELATED LINKS

[New-AzureRmIntegrationAccountMap]()

[Set-AzureRmIntegrationAccountMap]()

[Remove-AzureRmIntegrationAccountMap]()

