---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393046
schema: 2.0.0
---

# Stop-AzureRmResourceGroupDeployment

## SYNOPSIS
Cancels a resource group deployment

## SYNTAX

### The deployment name parameter set. (Default)
```
Stop-AzureRmResourceGroupDeployment [-ResourceGroupName] <String> [-Name] <String> [-Force]
 [<CommonParameters>]
```

### The deployment Id parameter set.
```
Stop-AzureRmResourceGroupDeployment -Id <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Stop-AzureRmResourceGroupDeployment cmdlet cancels an Azure resource group deployment that is started, but not completed.
To stop a deployment, the deployment must have an incomplete provisioning state, such as Provisioning, and not a completed state, such as Provisioned or Failed.An Azure resource is a user-managed entity, such as a website, database, or database server.
A resource group is a collection of resources that are deployed as a unit.
To deploy a resource group, use the New-AzureRmResourceGroup or New-AzureRmResourceGroupDeployment cmdlets.
The New-AzureRmResource cmdlet creates a new resource, but it does not trigger a resource group deployment operation that this cmdlet can stop.This cmdlet stops only one running deployment.
Use the Name parameter to stop a particular deployment.
If you omit the Name parameter, Stop-AzureRmResourceGroupDeployment searches for a running deployment and stops it, but if it finds more than one running deployment, the command fails.By default, Stop-AzureRmResourceGroupDeployment prompts you for confirmation.
To suppress the prompt, use the Force parameter.

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Force
Suppresses the confirmation prompt.
By default, Stop-AzureRmResourceGroupDeployment prompts you before stopping a deployment.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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
Stops the specified deployment.
Enter the deployment name.
This parameter is optional.Without this parameter, Stop-AzureRmResourceGroupDeployment searches for a running deployment in the resource group and stops it, but if it finds more than one running deployment, the command fails.You can use -Name or its alias, -DeploymentName.To find the deployment name, use the Get-AzureRmResourceGroupDeployment cmdlet.

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
Stops the deployment of the specified resource group.
This parameter is required.

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

### None

## OUTPUTS

### None or Boolean

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

