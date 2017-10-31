---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmLogicApp

## SYNOPSIS
Updates a new Logic App in an azure resource group.

## SYNTAX

```
Set-AzureRmLogicApp -ResourceGroupName <String> -Name <String> [-AppServicePlan <String>] [-State <String>]
 [-DefinitionLinkUri <String>] [-DefinitionLinkContentVersion <String>] [-Definition <Object>]
 [-DefinitionFilePath <String>] [-ParameterLinkUri <String>] [-ParameterLinkContentVersion <String>]
 [-Parameters <Object>] [-ParameterFilePath <String>] [-Force] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Set-AzureRmLogicApp cmdlet updates an Azure Logic App and returns an object that represents the Workflow.
Use this cmdlet to update a Logic App.
You can update a Logic App with a name, Logic App definition, resource group name, App Service Plan name.
However, typically, you use a Logic App template for definition and parameters which is JSON-based model.
To update a Logic App, you can specify definition as DefinitionFilePath or DefinitionLinkUri parameters or as a Definition object(string).
To specify values for the Logic App template parameters, use a JSON-formatted parameter file (-ParameterFilePath) or a HashTable of parameter names and values (-Parameters) or ParametersLinkUri parameters.
To use the dynamic parameters, just type them in the command, or type a hyphen sign(-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.
Template parameter file values that you specify at the command line take precedence over template parameter values in a template parameter object.

## EXAMPLES

### --------------------------  Example 1 : Updates a Logic App  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Set-AzureRmLogicApp -ResourceGroupName "ResourceGroup1" -Name "LogicApp1" -State "Enabled" -AppServicePlan "ServicePlan1" -DefinitionFilePath "d:\workflows\Definition.json" -ParameterFilePath "d:\workflows\Parameters.json"
```

This command updates a Logic App

Id                           : /subscriptions/57b7034d-72d4-433d-ace2-a7460aed6a99/resourceGroups/LogicAppCmdletTest/providers/Microsoft.Logic/workflows/LogicApp1
Name                         : LogicApp1
Type                         : Microsoft.Logic/workflows
Location                     : westus
ChangedTime                  : 1/13/2016 2:41:39 PM
CreatedTime                  : 1/13/2016 2:41:39 PM
AccessEndpoint               : https://\<baseurl\>/subscriptions/57b7034d-72d4-433d-ace2-a7460aed6a99/resourcegroups/ResourceGroup1/providers/Microsoft.Logic/workflows/LogicApp1
State                        : Enabled
DefinitionLinkUri            : 
DefinitionLinkContentVersion : 
Definition                   : {$schema, contentVersion, parameters, triggers...}
ParametersLinkUri            : 
ParametersLinkContentVersion : 
Parameters                   : {\[destinationUri, Microsoft.Azure.Management.Logic.Models.WorkflowParameter\]}
SkuName                      : Standard
PlanName                     : ServicePlan1
PlanType                     : Microsoft.Web/ServerFarms
PlanId                       : /subscriptions/57b7034d-72d4-433d-ace2-a7460aed6a99/resourceGroups/ResourceGroup1/providers/Microsoft.Web/serverfarms/ServicePlan1
Version                      : 08587489107859952120

## PARAMETERS

### -AppServicePlan
Specifies the name of the App Service Plan.
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

### -Definition
Definition of the Logic App.
Expected type object or JSON-formatted string.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionFilePath
Path of a JSON-formatted definition file.

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

### -DefinitionLinkContentVersion
Specifies the content version of the Definition link Uri.

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

### -DefinitionLinkUri
Specifies Definition link Uri of the Logic App.
If DefinitionLinkUri is provided as parameter then user must provide the "DefinitionLinkContentVersion" parameter.

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

### -Force
Do not ask for confirmation.

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

### -ParameterFilePath
Path of a JSON-formatted parameter file.

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

### -ParameterLinkContentVersion
Specifies the content version of the Parameter Link Uri of the Logic App.

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

### -ParameterLinkUri
Specifies parameter link Uri of the Logic App.
If ParameterLinkUri is provided as parameter then user must provide the "ParameterLinkContentVersion" parameter.

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

### -Parameters
Parameters collection object of the Logic App.
Expected Type HashTable or Dictionary\<string,\> or Dictionary\<string, WorkflowParameter\>.

```yaml
Type: Object
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

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
Specifies a state of the Logic App.
Expected values e.g.
Enabled, Disabled

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### Microsoft.Azure.Management.Logic.Models.Workflow

## NOTES

## RELATED LINKS

[New-AzureRmLogicApp]()

[Get-AzureRmLogicApp]()

[Remove-AzureRmLogicApp]()

