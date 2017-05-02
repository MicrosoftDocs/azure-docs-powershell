---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393049
schema: 2.0.0
---

# Remove-AzureRmResourceGroupDeployment

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### The deployment name parameter set. (Default)
```
Remove-AzureRmResourceGroupDeployment [-ResourceGroupName] <String> [-Name] <String> [-Force]
 [<CommonParameters>]
```

### The deployment Id parameter set.
```
Remove-AzureRmResourceGroupDeployment -Id <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Force
Do not confirm the remove.

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

### -Id
The fully qualified resource Id of the deployment.
example: /subscriptions/{subId}/resourceGroups/{rgName}/providers/Microsoft.Resources/deployments/{deploymentName}

```yaml
Type: String
Parameter Sets: The deployment Id parameter set.
Aliases: DeploymentId, ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the deployment.

```yaml
Type: String
Parameter Sets: The deployment name parameter set.
Aliases: DeploymentName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group.

```yaml
Type: String
Parameter Sets: The deployment name parameter set.
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

