---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmLogicAppAccessKey

## SYNOPSIS
Gets the access keys of a specified Logic App.

## SYNTAX

```
Get-AzureRmLogicAppAccessKey -ResourceGroupName <String> -Name <String> [-AccessKeyName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmLogicAppAccessKey cmdlet retrieves access key of an Azure Logic App and returns an object that represents the WorkflowSecretKeys.
Use this cmdlet to get a Logic App access key from a specified resource group.
You can get a Logic App access key by specifying the Logic App name, resource group name and access key name.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get the access key of a Logic App from specified Azure resource group.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmLogicAppAccessKey -ResourceGroupName "ResourceGroup1" -Name "LogicApp1" -AccessKeyName "default"
```

This command gets an access key of a Logic App from the specified Azure resource group.

PrimarySecretKey   : \<value\>
SecondarySecretKey : \<value\>

### --------------------------  Example 2 : Gets all the access keys of a Logic App from specified Azure resource group.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmLogicAppAccessKey -ResourceGroupName "ResourceGroup1" -Name "LogicApp1"
```

This command gets all the access keys of a Logic App from the specified Azure resource group.

PrimarySecretKey   : \<value\>
SecondarySecretKey : \<value\>

## PARAMETERS

### -AccessKeyName
Specifies the name of the access key.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.WorkflowSecretKeys

## NOTES

## RELATED LINKS

[Get-AzureRmLogicAppAccessKey]()

