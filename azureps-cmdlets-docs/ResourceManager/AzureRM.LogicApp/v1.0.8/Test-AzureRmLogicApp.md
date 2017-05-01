---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Test-AzureRmLogicApp

## SYNOPSIS
Validates the Logic App definition in the azure resource group.

## SYNTAX

### LogicAppWithDefinitionParameterSet
```
Test-AzureRmLogicApp -ResourceGroupName <String> -Name <String> -Location <String> [-State <String>]
 [-Definition <Object>] [-IntegrationAccountId <String>] [-Parameters <Object>] [-ParameterFilePath <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

### LogicAppWithDefinitionFileParameterSet
```
Test-AzureRmLogicApp -ResourceGroupName <String> -Name <String> -Location <String> [-State <String>]
 [-DefinitionFilePath <String>] [-IntegrationAccountId <String>] [-Parameters <Object>]
 [-ParameterFilePath <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Test-AzureRmLogicApp cmdlet validates the Azure Logic App definition in the Azure resource group.
Use this cmdlet to validate a Logic App workflow definition in the specified resource group.
You can validate a Logic App by specifying the Logic App name, resource group name, location, state, integration account ID, or parameters.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Validates a Logic App with definition and parameter template file path  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\>Test-AzureRmLogicApp -ResourceGroupName "ResourceGroup1" -Name "LogicApp1" -Location "westus" -State "Enabled" -DefinitionFilePath "d:\workflows\Definition.json" -ParameterFilePath "d:\workflows\Parameters.json"
```

This command validates a new Logic App in the specified resource group.

### --------------------------  Example 2 : Validates a Logic App with definition and parameter objects  --------------------------
@{paragraph=PS C:\\\>}

```
PS C:\>Test-AzureRmLogicApp -ResourceGroupName "ResourceGroup1" -Name "LogicApp1" -Location "westus" -State "Enabled" -Definition [IO.File]::ReadAllText("d:\Workflows\Definition.json") -Parameters @{name1="value1", name2="value2"}
```

This command validates a new Logic App in the targeted resource group.

## PARAMETERS

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

### -Name
Specifies the name of the Logic App.
This parameter is required.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
Specifies the location of the Logic App.
This parameter is required.
Enter an Azure data center location, such as "West US" or "Southeast Asia".
You can place a Logic App in any location.

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

### -Definition
Definition of the Logic App.
Expected type object or JSON-formatted string.

```yaml
Type: Object
Parameter Sets: LogicAppWithDefinitionParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntegrationAccountId
Specifies the integration account ID used for the LogicApp.
This parameter is optional.
e.g.
"/subscriptions/valid-subscription-guid/resourceGroups/valid-group-name/providers/Microsoft.Logic/integrationAccounts/valid-name-of-integration-account"

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

### -DefinitionFilePath
Path of a JSON-formatted definition file.

```yaml
Type: String
Parameter Sets: LogicAppWithDefinitionFileParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

