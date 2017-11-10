---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmIntegrationAccount

## SYNOPSIS
Gets the specified integration account from the Azure resource group.

## SYNTAX

```
Get-AzureRmIntegrationAccount [-ResourceGroupName <String>] [-Name <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmIntegrationAccount cmdlet retrieves integration account from the Azure resource group and returns an object that represents the integration account.
Use this cmdlet to get the integration account from specified resource group.
You can get the integration account by specifying the integration account name and resource group name.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get the integration account by name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccount -ResourceGroupName "Resourcegroup1" -Name "IntegrationAccount1"
```

This command gets the integration account from a specified resource group.

Id          : /subscriptions/\<SubscriptionId\>/resourceGroups/\<ResourceGroup1\>/providers/Microsoft.Logic/integrationAccounts/IntegrationAccount1
Name        : IntegrationAccount1
Type        : Microsoft.Logic/integrationAccounts
Location    : brazilsouth
Sku         :
CreatedTime : 3/26/2016 4:26:07 PM
ChangedTime : 3/26/2016 4:26:07 PM

### --------------------------  Example 2 : Get the integration account by resource group name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccount -ResourceGroupName "Resourcegroup1"
```

This command gets the integration account(s) from a specified resource group.

Id          : /subscriptions/\<SubscriptionId\>/resourceGroups/\<ResourceGroup1\>/providers/Microsoft.Logic/integrationAccounts/IntegrationAccount1
Name        : IntegrationAccount1
Type        : Microsoft.Logic/integrationAccounts
Location    : brazilsouth
Sku         :
CreatedTime : 3/26/2016 4:26:07 PM
ChangedTime : 3/26/2016 4:26:07 PM

### --------------------------  Example 3 : Get the integration accounts by subscription.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccount
```

This command gets all the integration account(s) in the subscription.

Id          : /subscriptions/\<SubscriptionId\>/resourceGroups/\<ResourceGroup1\>/providers/Microsoft.Logic/integrationAccounts/IntegrationAccount1
Name        : IntegrationAccount1
Type        : Microsoft.Logic/integrationAccounts
Location    : brazilsouth
Sku         :
CreatedTime : 3/26/2016 4:26:07 PM
ChangedTime : 3/26/2016 4:26:07 PM

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
This parameter is optional.

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

### Microsoft.Azure.Management.Logic.Models.IntegrationAccount

## NOTES

## RELATED LINKS

[Remove-AzureRmIntegrationAccount]()

[New-AzureRmIntegrationAccount]()

[Get-AzureRmIntegrationAccountCallbackUrl]()

[Set-AzureRmIntegrationAccount]()

