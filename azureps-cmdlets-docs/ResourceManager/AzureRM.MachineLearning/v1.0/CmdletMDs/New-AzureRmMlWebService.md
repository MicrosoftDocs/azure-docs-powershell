---
external help file: Microsoft.Azure.Commands.MachineLearning.dll-Help.xml
online version: .\Export-AzureRmMlWebService.md
schema: 2.0.0
---

# New-AzureRmMlWebService

## SYNOPSIS
Creates a web service resource.

## SYNTAX

### Create a new Azure ML webservice from a JSON definiton file.
```
New-AzureRmMlWebService -ResourceGroupName <String> -Location <String> -Name <String> -DefinitionFile <String>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Create a new Azure ML webservice from a WebService instance definition.
```
New-AzureRmMlWebService -ResourceGroupName <String> -Location <String> -Name <String>
 -NewWebServiceDefinition <WebService> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmMlWebService** cmdlet creates an azure_2 Machine Learning web service resource in a new or existing resource group.
If a resource with the same name exists in the resource group, the cmdlet acts as an update operation and overwrites the existing web service resource.

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

Alternatively, to determine the resource group name of an existing web service, log on to the Microsoft azure_2 Machine Learning Web Services portal.
Select the web service.
The resource group name is the fifth element of the URL of the web service, just after the **resourceGroups** element.
In the following example the resource group name is **Default-MachineLearning-SouthCentralUS**.

`https://services.azureml.net/subscriptions/\<subcription ID\>/resourceGroups/Default-MachineLearning-SouthCentralUS/providers/Microsoft.MachineLearning/webServices/Sample5TrainTest.2016.7.22.15.46.31.322`

## EXAMPLES

### Example 1: Create a new service from a Json file based definition
```
PS C:\>New-AzureRmMlWebService -ResourceGroupName "RG001" -Name "WebService002" -Location "South Central US" -DefinitionFile "C:\mlservice.json"
```

This command creates an azure_2 Machine Learning web service resource named WebService002 that belongs to the resource group named RG001.
This command also sets the location to South Central US, based on the definition present in the referenced json file.

### Example 2: Create a new service from an object instance
```
PS C:\>New-AzureRmMlWebService -ResourceGroupName "RG004" -Name "WebService005" -Location "South Central US" -NewWebServiceDefinition $ServiceDefinitionObject
```

This command creates an azure_2 Machine Learning web service resource named WebService005 that belongs to the resource group named RG004.
This command also sets the location to South Central US.
The new web service uses the information stored in the $ServiceDefinitionObject to create the definition.
You can obtain a web service object instance to customize before publishing as a resource by using the Import-AzureRmMlWebService cmdlet.

## PARAMETERS

### -ResourceGroupName
Specifies the resource group that this web service belongs to.
Enter the name an existing resource group that was provisioned ahead of this web service resource.

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

### -Location
Specifies the location of the web service resource.
Enter an azure_2 data center location, such as West US or Southeast Asia.
You can place a resource in any location that supports resources of that type.
The resource does not have to be in the same location your azure_2 subscription or the same location as its resource group.
Resource groups can contain resources from different locations.
To determine which locations support each resource type, use the Get-AzureRmResourceProvider cmdlet with the *ProviderNamespace* parameter cmdlet.

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
Specifies the name for the web service resource.
The value for the *Name* parameter must be unique in the resource group.

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

### -DefinitionFile
Specifies the path to a file on disk containing the definition of the web service resource, in JSON format.
You can find the latest specification for the web service definition in the swagger specification file under https://github.com/Azure/azure-rest-api-specs/tree/master/arm-machinelearninghttps://github.com/Azure/azure-rest-api-specs/tree/master/arm-machinelearning(https://github.com/Azure/azure-rest-api-specs/tree/master/arm-machinelearning).

```yaml
Type: String
Parameter Sets: Create a new Azure ML webservice from a JSON definiton file.
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewWebServiceDefinition
Specifies the definition of the web service resource, that contains all the properties that make up the service.
This parameter is required and represents an instance of the **Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService** class.
You can find the latest specification for the web service definition in the swagger specification under https://github.com/Azure/azure-rest-api-specs/blob/master/arm-machinelearning/2016-05-01-preview/swagger/webservices.json.https://github.com/Azure/azure-rest-api-specs/blob/master/arm-machinelearning/2016-05-01-preview/swagger/webservices.json (https://github.com/Azure/azure-rest-api-specs/blob/master/arm-machinelearning/2016-05-01-preview/swagger/webservices.json).
This parameter can come from a pipeline.

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

### -Force
ps_force

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

### -Confirm
psdx_confirmdesc

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
psdx_whatifdesc

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
The summary description of the created azure_2 Machine Learning web service resource is similar to the result obtained when calling the Get-AzureRmMlWebService cmdlet for an existing web service.
This description does not contain sensitive properties.

## NOTES
* Keywords: azure, azurerm, arm, resource, management, manager, machine, machine learning, azureml

## RELATED LINKS

[Export-AzureRmMlWebService](.\Export-AzureRmMlWebService.md)

[Get-AzureRmMlWebService](.\Get-AzureRmMlWebService.md)

[Import-AzureRmMlWebService](.\Import-AzureRmMlWebService.md)

[Remove-AzureRmMlWebService](.\Remove-AzureRmMlWebService.md)

[Update-AzureRmMlWebService](.\Update-AzureRmMlWebService.md)

