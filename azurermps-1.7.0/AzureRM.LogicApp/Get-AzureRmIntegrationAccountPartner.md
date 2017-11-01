---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmIntegrationAccountPartner

## SYNOPSIS
Gets the specified integration account partner from the Azure resource group.

## SYNTAX

```
Get-AzureRmIntegrationAccountPartner [-ResourceGroupName <String>] [-Name <String>] [-PartnerName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmIntegrationAccountPartner cmdlet retrieves integration account partner from the Azure resource group and returns an object that represents the integration account partner.
Use this cmdlet to get the integration account partner from specified resource group.
You can get the integration account partner by specifying the integration account name, resource group name and partner name.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get the integration account partner by name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountPartner -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -PartnerName "IntegrationAccountPartner1"
```

This command gets the integration account partner by name.

Id                 : /subscriptions/\<SubscriptionId\>/resourceGroups/ResourceGroup1/providers/Microsoft.Logic/integrationAccounts/TestIntegrationAccount/partners/IntegrationAccountPartner1
Name               : IntegrationAccountPartner1
Type               : Microsoft.Logic/integrationAccounts/partners
PartnerType        : B2B
CreatedTime        : 3/24/2016 8:46:05 PM
ChangedTime        : 3/24/2016 8:47:47 PM
BusinessIdentities : {"Qualifier":"CC","Value":"FF"}
Metadata           :

### --------------------------  Example 2 : Get the integration account partners by integration account name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountPartner -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1"
```

This command gets the integration account partners by integration account name.

Id                 : /subscriptions/\<SubscriptionId\>/resourceGroups/ResourceGroup1/providers/Microsoft.Logic/integrationAccounts/TestIntegrationAccount/partners/IntegrationAccountPartner1
Name               : IntegrationAccountPartner1
Type               : Microsoft.Logic/integrationAccounts/partners
PartnerType        : B2B
CreatedTime        : 3/24/2016 8:46:05 PM
ChangedTime        : 3/24/2016 8:47:47 PM
BusinessIdentities : {"Qualifier":"CC","Value":"FF"}
Metadata           :

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

### -PartnerName
Specifies a name for the integration account partner.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.IntegrationAccountPartner

## NOTES

## RELATED LINKS

[New-AzureRmIntegrationAccountPartner]()

[Set-AzureRmIntegrationAccountPartner]()

[Remove-AzureRmIntegrationAccountPartner]()

