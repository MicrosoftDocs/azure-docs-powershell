---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmIntegrationAccountSchema

## SYNOPSIS
Gets the specified integration account schema from the Azure resource group.

## SYNTAX

```
Get-AzureRmIntegrationAccountSchema [-ResourceGroupName <String>] [-Name <String>] [-SchemaName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmIntegrationAccountSchema cmdlet retrieves integration account schema from the Azure resource group and returns an object that represents the integration account schema.
Use this cmdlet to get the integration account schema from specified resource group.
You can get the integration account schema by specifying the integration account name, resource group name and schema name.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get the integration account schema by name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountSchema -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -SchemaName "IntegrationAccountSchema1"
```

This commands gets the integration account schema by name.

Id                   : /subscriptions/\<SubscriptionId\>/resourceGroups/ResourceGroup1/providers/Microsoft.Logic/integrationAccounts/IntegrationAccount1/schemas/IntegrationAccountSchema1
Name                 : IntegrationAccountSchema1
Type                 : Microsoft.Logic/integrationAccounts/schemas
CreatedTime          : 3/25/2016 5:42:58 PM
ChangedTime          : 3/25/2016 5:42:58 PM
SchemaType           : Xml
ContentType          : 
ContentLink          : https://\<baseurl\>/integrationaccounts469af4f3cf4047b7ac3a08c87948ec5f/3839E_XML_INTEGRATIONACCOUNTSCHEMA1-5A86631F61F
                       14513AA1185A52C6B2874?sv=2014-02-14&sr=b&sig=\<value\>
ContentSize          : 7901
MetaData             :

### --------------------------  Example 2 : Get the integration account schemas by resource group name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountSchema -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1"
```

This command gets the integration account schemas by resource group name.

Id                   : /subscriptions/\<SubscriptionId\>/resourceGroups/ResourceGroup1/providers/Microsoft.Logic/integrationAccounts/IntegrationAccount1/schemas/IntegrationAccountSchema1
Name                 : IntegrationAccountSchema1
Type                 : Microsoft.Logic/integrationAccounts/schemas
CreatedTime          : 3/25/2016 5:42:58 PM
ChangedTime          : 3/25/2016 5:42:58 PM
SchemaType           : Xml
ContentType          : 
ContentLink          : https://\<baseurl\>/integrationaccounts469af4f3cf4047b7ac3a08c87948ec5f/3839E_XML_INTEGRATIONACCOUNTSCHEMA1-5A86631F61F
                       14513AA1185A52C6B2874?sv=2014-02-14&sr=b&sig=\<value\>
ContentSize          : 7901
MetaData             :

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

### -Name
Specifies a name for the integration account.
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

### -SchemaName
Specifies a name for the schema.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.IntegrationAccountSchema

## NOTES

## RELATED LINKS

[Set-AzureRmIntegrationAccountSchema]()

[New-AzureRmIntegrationAccountSchema]()

[Remove-AzureRmIntegrationAccountSchema]()

