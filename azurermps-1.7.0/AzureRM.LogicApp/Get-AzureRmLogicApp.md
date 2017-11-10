---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmLogicApp

## SYNOPSIS
Gets the specified Logic App from the Azure resource group.

## SYNTAX

```
Get-AzureRmLogicApp -ResourceGroupName <String> -Name <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmLogicApp cmdlet retrieves Azure Logic App from the Azure resource group and returns an object that represents the Workflow.
Use this cmdlet to get a Logic App from specified resource group.
You can get a Logic App by specifying the Logic App name and resource group name.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get a Logic App from specified Azure resource group.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmLogicApp -ResourceGroupName "ResourceGroup1" -Name "LogicApp1"
```

This command gets a Logic App from the specified Azure resource group.

Id                           : /subscriptions/\<subscriptionid\>/resourceGroups/\<ResourceGroup\>/providers/Microsoft.Logic/workflows/LogicApp1
Name                         : LogicApp1
Type                         : Microsoft.Logic/workflows
Location                     : westus
ChangedTime                  : 1/13/2016 2:41:39 PM
CreatedTime                  : 1/13/2016 2:41:39 PM
AccessEndpoint               : https://\<baseurl\>/subscriptions/\<susbcriptionid\>/resourcegroups/\<ResourceGroup\>/providers/Microsoft.Logic/workflows/LogicApp1
State                        : Enabled
DefinitionLinkUri            : 
DefinitionLinkContentVersion : 
Definition                   : {$schema, contentVersion, parameters, triggers...}
ParametersLinkUri            : 
ParametersLinkContentVersion : 
Parameters                   : {\[destinationUri, Microsoft.Azure.Management.Logic.Models.WorkflowParameter\]}
SkuName                      : Standard
PlanName                     : StandardServicePlan
PlanType                     : Microsoft.Web/ServerFarms
PlanId                       : /subscriptions/\<subscriptionid\>/resourceGroups/\<ResourceGroup\>/providers/Microsoft.Web/serverfarms/StandardServicePlan
Version                      : 08587489107859952120

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
Specifies the name of the Logic App.
This parameter is required.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.Workflow

## NOTES

## RELATED LINKS

[New-AzureRmLogicApp]()

[Set-AzureRmLogicApp]()

[Remove-AzureRmLogicApp]()

