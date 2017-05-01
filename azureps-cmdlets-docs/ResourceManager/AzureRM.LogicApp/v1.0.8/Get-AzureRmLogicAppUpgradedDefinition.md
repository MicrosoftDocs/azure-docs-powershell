---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmLogicAppUpgradedDefinition

## SYNOPSIS
Gets the upgraded definition for specified LogicApp from the Azure resource group.

## SYNTAX

```
Get-AzureRmLogicAppUpgradedDefinition -ResourceGroupName <String> -Name <String> -TargetSchemaVersion <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>]
```

## DESCRIPTION
The Get-AzureRmLogicAppUpgradedDefinition cmdlet retrieves the upgraded definition for specified schema version and specified LogicApp from the Azure resource group and returns an object that represents the definition of the upgraded LogicApp.
Use this cmdlet to upgrade the definition to a higher schema version.
You can get the upgraded definition by specifying the resource group name, LogicApp name, and target schema version.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get a Logic App upgraded definition.  --------------------------
@{paragraph=PS C:\\\>}

```
$upgradedDefinition = Get-AzureRmLogicAppUpgradedDefinition -ResourceGroupName "Resourcegroup1" -Name "LogicApp1" -TargetSchemaVersion "2016-06-01"
$upgradedDefinition.ToString()
```

Gets the definition for the Logic App upgraded to the provided target schema version.

{
  "$schema": "http://schema.management.azure.com/providers/Microsoft.Logic/schemas/2016-06-01/workflowdefinition.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {},
  "triggers": {
    "httpTrigger": {
      "recurrence": {
        "frequency": "Hour",
        "interval": 1
      },
      "type": "Http",
      "inputs": {
        "method": "GET",
        "uri": "http://www.bing.com"
      },
      "conditions": \[
        {
          "expression": "@bool('true')"
        }
      \]
    },
    "manualTrigger": {
      "type": "Request",
      "kind": "Http"
    }
  },
  "actions": {
    "httpScope": {
      "actions": {
        "http": {
          "runAfter": {},
          "type": "Http",
          "inputs": {
            "method": "GET",
            "uri": "http://www.bing.com"
          }
        }
      },
      "runAfter": {},
      "else": {
        "actions": {}
      },
      "expression": "@bool('true')",
      "type": "If"
    },
    "http1Scope": {
      "actions": {
        "http1": {
          "runAfter": {},
          "type": "Http",
          "inputs": {
            "method": "GET",
            "uri": "http://www.bing.com"
          }
        }
      },
      "runAfter": {},
      "else": {
        "actions": {}
      },
      "expression": "@bool('true')",
      "type": "If"
    }
  },
  "outputs": {
    "output1": {
      "type": "String",
      "value": "true"
    }
  }
}

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
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetSchemaVersion
Specifies the target schema version for the definition.
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

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

