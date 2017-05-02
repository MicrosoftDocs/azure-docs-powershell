---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393044
schema: 2.0.0
---

# Get-AzureRmResourceGroupDeploymentOperation

## SYNOPSIS
Gets the resource group deployment operation

## SYNTAX

```
Get-AzureRmResourceGroupDeploymentOperation -DeploymentName <String> [-SubscriptionId <Guid>]
 -ResourceGroupName <String> [-ApiVersion <String>] [-Pre] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This lists all the operations that were part of a deployment.
It can be used for debugging deployment failures as it will help you identify and give more information about the exact operations that failed for a particular deployment.
It can also give out the response and the request content for each deployment operation.
This is the same information that you get from the deployment details on the portal.

For getting the request and the response content, the setting will have to be enabled when submitting a deployment through New-AzureRmResourceGroupDeployment.
It can potentially log and expose secrets like passwords used in the resource property or listKeys operations that are then returned when you retrieve the deployment operations.
For more details on this setting and how to enable it, please see the help for New-AzureRmResourceGroupDeployment or https://aka.ms/deploymentdebug

If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Example 1 --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmResourceGroupDeploymentOperation -DeploymentName test -ResourceGroupName test
```

Gets deployment operation with name "test" under resource group "test"

### --------------------------  Example 2 --------------------------
@{paragraph=PS C:\\\>}



```
$operations = Get-AzureRmResourceGroupDeploymentOperation -DeploymentName test -ResourceGroupName test
          foreach($operation in $operations)
          {
              Write-Host $operation.id
              Write-Host "Request:"
              $operation.Properties.Request | ConvertTo-Json -Depth 10
              Write-Host "Response:"
              $operation.Properties.Response | ConvertTo-Json -Depth 10
          }
```

Gets deployment operation with name "test" under resource group "test" and lists all the request and response content associated with each deployment operation.

## PARAMETERS

### -ApiVersion
When set, indicates the version of the resource provider API to use.
If not specified, the API version is automatically determined as the latest available.

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

### -DeploymentName
The deployment name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

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

### -ResourceGroupName
The resource group name.

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

### -SubscriptionId
The subscription to use.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

