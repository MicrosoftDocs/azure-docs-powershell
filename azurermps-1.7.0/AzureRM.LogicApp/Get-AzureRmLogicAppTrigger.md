---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmLogicAppTrigger

## SYNOPSIS
Gets the specified trigger of the logic app.

## SYNTAX

```
Get-AzureRmLogicAppTrigger -ResourceGroupName <String> -Name <String> [-TriggerName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmLogicAppTrigger cmdlet retrieves the specified trigger from the logic app and returns an object/collection which represents the workflow trigger.
Use this cmdlet to get the trigger(s) of the logic app from a specified resource group.
You can get the logic app's trigger by specifying the workflow name, resource group name and trigger name.
To use the dynamic parameters, just type them in the command, or type a minus sign to indicate a parameter name (-) and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Gets the specified Logic App trigger of a Logic App in the specified Azure resource group.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmLogicAppTrigger -ResourceGroupName "Resourcegroup1" -Name "LogicApp1" -TriggerName "Trigger1"
```

This command gets the trigger of the specified Logic App and Azure resource group.

ChangedTime         : 1/14/2016 11:45:07 AM
CreatedTime         : 1/13/2016 2:42:26 PM
LastExecutionTime   : 1/14/2016 11:45:07 AM
Name                : Trigger1
NextExecutionTime   : 1/14/2016 12:45:07 PM
RecurrenceFrequency : Minute
RecurrenceInterval  : 60
Status              : Waiting
Type                : Microsoft.Logic/workflows/triggers
LogicAppName        : LogicApp1
LogicAppVersion     : 08587489107406290826

### --------------------------  Example 2 : Gets Logic App triggers of the Logic App from a specified Azure resource group.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmLogicAppTrigger -ResourceGroupName "Resourcegroup1" -Name "LogicApp1"
```

This command gets trigger(s) of the specified Logic App in the Azure resource group.

ChangedTime         : 1/14/2016 11:45:07 AM
CreatedTime         : 1/13/2016 2:42:26 PM
LastExecutionTime   : 1/14/2016 11:45:07 AM
Name                : Trigger1
NextExecutionTime   : 1/14/2016 12:45:07 PM
RecurrenceFrequency : Minute
RecurrenceInterval  : 60
Status              : Waiting
Type                : Microsoft.Logic/workflows/triggers
LogicAppName        : LogicApp1
LogicAppVersion     : 08587489107406290826

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
Specifies the name of the logic app.
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

### -TriggerName
Specifies the name of the trigger.
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

### Microsoft.Azure.Management.Logic.Models.WorkflowTrigger

## NOTES

## RELATED LINKS

[Get-AzureRmLogicAppTriggerHistory]()

[Start-AzureRmLogicApp]()

