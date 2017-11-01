---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393045
schema: 2.0.0
---

# New-AzureRmResourceGroupDeployment

## SYNOPSIS
Add an Azure deployment to a resource group.

## SYNTAX

### Deployment via template file without parameters (Default)
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateFile <String> [-ApiVersion <String>] [-Pre] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Deployment via template uri and template parameters object
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterObject <Hashtable> -TemplateUri <String>
 [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Deployment via template file and template parameters object
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterObject <Hashtable> -TemplateFile <String>
 [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Deployment via template uri and template parameters file
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterFile <String> -TemplateUri <String>
 [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Deployment via template file and template parameters file
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterFile <String> -TemplateFile <String>
 [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Deployment via template uri and template parameters uri
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterUri <String> -TemplateUri <String>
 [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Deployment via template file template parameters uri
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateParameterUri <String> -TemplateFile <String>
 [-ApiVersion <String>] [-Pre] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Deployment via template uri without parameters
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-DeploymentDebugLogLevel <String>] [-Force] -TemplateUri <String> [-ApiVersion <String>] [-Pre] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmResourceGroupDeployment cmdlet adds a deployment to an existing resource group, including the resources that the deployment requires.
To add resources to a resource group without using a template, use the New-AzureRmResource cmdlet.

An Azure resource is a user-managed Azure entity, such as a database server, database, website, virtual machine, or storage account.
An Azure resource group is a collection of Azure resources that are deployed as a unit, such as the web site, database server, and databases that are required for a financial web site.
A deployment uses a resource group template to add resource to a resource group and publish them so they are available in Azure.

To add a resource group deployment, specify the name of an existing resource group and a resource group template, which is a JSON string that represents of a resource group for a complex cloud-based service, such as a web portal.
The template includes parameter (placeholders) for required resources and configurable property values, likes names and sizes.
You can find many templates in the Azure template gallery and you can create your own templates.

You can also create a custom resource group template, either by typing in a text file  or by editing a gallery template.
To use a custom template to create a resource group, use TemplateFile or TemplateUri parameters to supply the location and file name.
Each template has different parameters for configurable properties.
To specify values for the template parameters, use a JSON-formatted parameter file (TemplateParameterFile parameter) or a hash table of parameter names and values (TemplateParameterObject parameter).
Or, use the template parameters that are added to the command dynamically as soon as you specify a template.
To use the dynamic parameters, just type them in the command, or type a minus sign to indicate a parameter name (-) and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required parameter, the cmdlet prompts you for the value.
Template parameter values that are typed at the command line take precedence over values in a template parameter object or file.

For more information about deploying template, please refer https://azure.microsoft.com/en-us/documentation/articles/resource-group-template-deploy/

If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Example 1: Use a custom template and parameter file  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResourceGroupDeployment -ResourceGroupName ContosoEngineering -TemplateFile D:\Azure\Templates\EngineeringSite.json -TemplateParameterFile D:\Azure\Templates\EngSiteParms.json
```

This command creates a new deployment by using a custom template and a template file on disk.
The command uses the TemplateFile parameter to specify the template and the TemplateParameterFile to specify a file of parameters and parameter values.

### --------------------------  Example 2: Use a custom template uri and parameter uri with "Incremental" mode --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResourceGroupDeployment -Name testDeployment -ResourceGroupName ContosoEngineering
          -TemplateUri https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.json
          -TemplateParameterUri https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.parameters.json
          -Mode Incremental
          -DeploymentDebugSetting All
```

This command creates a new deployment by using a custom template and a template file from the quickstart gallery on github.
The command uses the TemplateUri parameter to specify the template and the TemplateParameterUri to specify the parameters.

It also sets the Mode to "Incremental" which will do an update to the deployment.
If a resource already exists in the resource group it will skip that resource and deploy the next one.

It sets the DeploymentDebugLevel to All.
This setting will log the request content and response content for each deployment operation associated with the deployment.
This data can be later retrieved by using the Get-AzureRmResourceGroupDeploymentOperation cmdlet.

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

### -DeploymentDebugLogLevel
This is used to log the request content, the response content or both associated with each deployment operation in the deployment.
The allowed values are RequestContent, ResponseContent, All or None.

If value is set to RequestContent,  the content associated with the http request for each deployment operation will be logged.
The type of content is JToken.
The content of the write request of the operation will be logged.
Ex- content of PUT in case of create resource

If value is set to ResponseContent, the content associated with the http response for each deployment operation will be logged.
It will be the content of the last response of that operation.

All will log both request and response content and None or not specifying this setting will not log either.

Note: You can potentially log and expose secrets like passwords used in the resource property or listKeys operations that are then returned when you retrieve the deployment operations.
More details can be found at https://aka.ms/deploymentdebug

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

### -Force
Do not ask for confirmation

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

### -Mode
The deployment mode to use.
Default is Incremental.
If 'Complete' deployment mode is used, existing resources in the resource group that are not included in the template will be deleted.
For more information, please refer to https://azure.microsoft.com/en-us/documentation/articles/resource-group-template-deploy/

```yaml
Type: DeploymentMode
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the deployment project for the resource group.
Use -Name or its alias -DeploymentName.
This parameter is optional.
The default value is the template name without the .json file name extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DeploymentName

Required: False
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

### -ResourceGroupName
Specifies the name of the resource group to which this deployment is added.
This parameter is required.
If the resource group does not exist, the command fails.

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

### -TemplateFile
Specifies the path and file name of a JSON template file on disk.
This can be a custom template or a gallery template that is saved to disk as a JSON file.

```yaml
Type: String
Parameter Sets: Deployment via template file without parameters, Deployment via template file and template parameters object, Deployment via template file and template parameters file, Deployment via template file template parameters uri
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateParameterFile
Specifies the path and name of a JSON file with the names and values of the template parameters.
This parameter is optional.If a template has parameters, you must specify parameter values, but you can use this parameter or the TemplateParameterObject parameter.
Also, the template parameters are added to the command dynamically when you specify a template.
To use the dynamic parameters, just type them in the command, or type a minus sign to indicate a parameter name (-) and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required parameter, the cmdlet prompts you for the value.

```yaml
Type: String
Parameter Sets: Deployment via template uri and template parameters file, Deployment via template file and template parameters file
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateParameterObject
Specifies a hash table of template parameter names and values.
This parameter is optional.
For help with hash tables in Windows PowerShell, type: Get-Help about_Hash_Tables.If a template has parameters, you must specify parameter values, but you can use this parameter or the TemplateParameterObject parameter.
Also, the template parameters are added to the command dynamically when you specify a template.
To use the dynamic parameters, just type them in the command, or type a minus sign to indicate a parameter name (-) and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required parameter, the cmdlet prompts you for the value.

```yaml
Type: Hashtable
Parameter Sets: Deployment via template uri and template parameters object, Deployment via template file and template parameters object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateParameterUri
Uri to the template parameter file.

```yaml
Type: String
Parameter Sets: Deployment via template uri and template parameters uri, Deployment via template file template parameters uri
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateUri
Specifies the URI of a JSON template file.
This file can be a custom template or a gallery template that is saved as a JSON file.

```yaml
Type: String
Parameter Sets: Deployment via template uri and template parameters object, Deployment via template uri and template parameters file, Deployment via template uri and template parameters uri, Deployment via template uri without parameters
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Models.PSResourceGroupDeployment

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

