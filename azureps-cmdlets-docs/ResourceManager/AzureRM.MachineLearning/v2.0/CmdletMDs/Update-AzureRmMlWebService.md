---
external help file: Microsoft.Azure.Commands.MachineLearning.dll-Help.xml
online version: .\Export-AzureRmMlWebService.md
schema: 2.0.0
---

# Update-AzureRmMlWebService

## SYNOPSIS
Updates properties of an existing web service resource.

## SYNTAX

### Update specific properties of the .
```
Update-AzureRmMlWebService -ResourceGroupName <String> -Name <String> [-Title <String>] [-Description <String>]
 [-IsReadOnly] [-Keys <WebServiceKeys>] [-StorageAccountKey <String>] [-Diagnostics <DiagnosticsConfiguration>]
 [-RealtimeConfiguration <RealtimeConfiguration>] [-Assets <Hashtable>]
 [-Input <ServiceInputOutputSpecification>] [-Output <ServiceInputOutputSpecification>]
 [-Parameters <Hashtable>] [-Package <GraphPackage>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Create a new Azure ML webservice from a WebService instance definition.
```
Update-AzureRmMlWebService -ResourceGroupName <String> -Name <String> -ServiceUpdates <WebService> [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-AzureRmMlWebService** cmdlet updates properties of an Azure Machine Learning web service.
The cmdlet works as a patch operation, so you need to pass only the properties that you want to modify.

To determine the resource group name of an existing web service, run the Get-AzureRmMlWebService cmdlet to display the web services in your subscription.
Locate the web service, and then look at its web service ID.
The name of the resource group is the fourth element in the ID, just after the **resourceGroups** element.
In the following example the resource group name is **Default-MachineLearning-SouthCentralUS**.

`Properties : Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebServicePropertiesForGraph`
`Id         : /subscriptions/\<subscription ID\>/resourceGroups/Default-MachineLearning-SouthCentralUS/providers/Microsoft.MachineLearning/webServices/Sample5TrainTest.2016.7.22.15.46.31.322`
`Name       : Sample5TrainTest.2016.7.22.15.46.31.322`
`Location   : South Central US`
`Type       : Microsoft.MachineLearning/webServices`
`Tags       : {}`

Alternatively, to determine the resource group name of an existing web service, log on to the Microsoft Azure Machine Learning Web Services portal.
Select the web service.
The resource group name is the fifth element of the URL of the web service, just after the **resourceGroups** element.
In the following example the resource group name is **Default-MachineLearning-SouthCentralUS**.

`https://services.azureml.net/subscriptions/\<subcription ID\>/resourceGroups/Default-MachineLearning-SouthCentralUS/providers/Microsoft.MachineLearning/webServices/Sample5TrainTest.2016.7.22.15.46.31.322`

## EXAMPLES

### Example 1: Update selective properties of an Azure Machine Learning web service
```
PS C:\>Update-AzureRmMlWebService -ResourceGroupName "RG002" -Name "WebService002" -Description "new update to description" -Keys @{Primary='changed primary key'} -Diagnostics @{Level='All'}
```

This command changes the description, primary access key, and enables the diagnostics collection for all traces during runtime for the web service named WebService002.

### Example 2: Update an Azure Machine Learning web service based on a web service instance
```
PS C:\>$Updates = @{ Properties = @{ Title="New Title"; RealtimeConfiguration = @{ MaxConcurrentCalls=25 }}}
PS C:\> Update-AzureRmMlWebService -ResourceGroupName "RG001" -Name " WebService001" -ServiceUpdates $Updates
```

The first command creates a web service definition that contains the fields to be updated and stores the results in the variable named $Updates.
The second command calls the **Update-AzureRmMlWebService** cmdlet to apply those service updates stored in the $Updates variable for the web service named WebService001 that belongs to the resource group named RG001.

## PARAMETERS

### -ResourceGroupName
Specifies the resource group that the web service belongs to.

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

### -Name
Specifies the name of the web service resource that this cmdlet updates.

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

### -Title
Specifies the update value for the title of the web service.
The value of the parameter is visible in the service's Swagger API schema.

```yaml
Type: String
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies the description for the update value for the web service.
This parameter is visible in the service's Swagger API schema.

```yaml
Type: String
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
Indicates that this cmdlet sets this web service to be read only, which means that the service is no longer updateable and can only be deleted.

```yaml
Type: SwitchParameter
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Keys
Specifies one or both of the access keys used to authenticate calls to the service's runtime APIs.

```yaml
Type: WebServiceKeys
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountKey
Specifies the access key for the storage account associated with the web service.

```yaml
Type: String
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Diagnostics
Specifies the settings controlling the diagnostics traces collection for the web service.

```yaml
Type: DiagnosticsConfiguration
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RealtimeConfiguration
Specifies the **RealtimeConfiguration** object for the web service's realtime endpoint.

```yaml
Type: RealtimeConfiguration
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Assets
Specifies the set of assets that make up the web service.
Assets include, but are not limited to, modules and datasets.

```yaml
Type: Hashtable
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Input
Specifies the definition for input of the web service, provided as a Swagger schema construct.

```yaml
Type: ServiceInputOutputSpecification
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Output
Specifies the definition for the output of the web service, provided as a Swagger schema construct.

```yaml
Type: ServiceInputOutputSpecification
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Specifies, as a hashtable, the set of global parameters values defined for the web service, given as a global parameter name -\> default value collection.

```yaml
Type: Hashtable
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Package
Specifies the definition of the graph package making up this web service.

```yaml
Type: GraphPackage
Parameter Sets: Update specific properties of the .
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -ServiceUpdates
Specifies a set of updates to apply to the web service provided as a web service definition instance.
The updateable fields are modified from this definition reference.
This parameter can be used on the pipeline.

```yaml
Type: WebService
Parameter Sets: Create a new Azure ML webservice from a WebService instance definition.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## NOTES
* Keywords: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## RELATED LINKS

[Export-AzureRmMlWebService](.\Export-AzureRmMlWebService.md)

[Get-AzureRmMlWebService](.\Get-AzureRmMlWebService.md)

[Import-AzureRmMlWebService](.\Import-AzureRmMlWebService.md)

[New-AzureRmMlWebService](.\New-AzureRmMlWebService.md)

[Remove-AzureRmMlWebService](.\Remove-AzureRmMlWebService.md)

