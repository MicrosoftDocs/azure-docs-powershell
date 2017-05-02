---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmPolicyAssignment

## SYNOPSIS
Updates existing policy assignment

## SYNTAX

### The policy assignment name parameter set. (Default)
```
Set-AzureRmPolicyAssignment -Name <String> -Scope <String> [-DisplayName <String>] [-ApiVersion <String>]
 [-Pre] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### The policy assignment Id parameter set.
```
Set-AzureRmPolicyAssignment -Id <String> [-DisplayName <String>] [-ApiVersion <String>] [-Pre]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Updates existing policy assignment

If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Update the display name on an existing policy assignment  --------------------------
@{paragraph=PS C:\\\>}



```
$rg = Get-AzureRmResourceGroup -Name testGroup
          $policyAssignment = Get-AzureRmPolicyAssignment -Name myPolicyAssignment -Scope $rg.ResourceId
          Set-AzureRmPolicyAssignment -Id $policyAssignment.ResourceId -DisplayName "Do not allow VM creation"
```

Updates the display name on an existing policy assignment

## PARAMETERS

### -ApiVersion
@{Text=}

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

### -DisplayName
The display name for policy assignment

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

### -Id
The fully qualified resource Id for the policy assignment

```yaml
Type: String
Parameter Sets: The policy assignment Id parameter set.
Aliases: ResourceId

Required: True
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
The policy assignment name

```yaml
Type: String
Parameter Sets: The policy assignment name parameter set.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pre
When set, indicates that the cmdlet should use pre-release API versions when automatically determining which version to use.

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

### -Scope
The scope at which the policy assignment is applied

```yaml
Type: String
Parameter Sets: The policy assignment name parameter set.
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

## NOTES

## RELATED LINKS

