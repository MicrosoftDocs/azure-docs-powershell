---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393054
schema: 2.0.0
---

# Test-AzureRmResourceGroupDeployment

## SYNOPSIS
Detects errors in a resource group template or template parameters

## SYNTAX

### Deployment via template file without parameters (Default)
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>] -TemplateFile <String>
 [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Deployment via template uri and template parameters object
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>]
 -TemplateParameterObject <Hashtable> -TemplateUri <String> [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Deployment via template file and template parameters object
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>]
 -TemplateParameterObject <Hashtable> -TemplateFile <String> [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Deployment via template uri and template parameters file
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>]
 -TemplateParameterFile <String> -TemplateUri <String> [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Deployment via template file and template parameters file
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>]
 -TemplateParameterFile <String> -TemplateFile <String> [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Deployment via template uri and template parameters uri
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>]
 -TemplateParameterUri <String> -TemplateUri <String> [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Deployment via template file template parameters uri
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>]
 -TemplateParameterUri <String> -TemplateFile <String> [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

### Deployment via template uri without parameters
```
Test-AzureRmResourceGroupDeployment -ResourceGroupName <String> [-Mode <DeploymentMode>] -TemplateUri <String>
 [-ApiVersion <String>] [-Pre] [<CommonParameters>]
```

## DESCRIPTION
The Test-AzureResourceGroupDeployment cmdlet verifies the validity of a resource group template, its parameters, and parameter values.
It returns errors that it finds.
Otherwise, it does not return any output.

To specify a template, use the TemplateUri or TemplateFile parameters.
To specify the template parameter values, use the TemplateParameterFile or TemplateParameterObject parameters, or use the template parameters that are added to the command dynamically when you specify the template.
To get the parameters, just type a minus sign (-) to indicate a parameter name and press the TAB key to trigger tab-completion.
If you miss a required parameter, the cmdlet prompts you for the value.
Parameter values typed at the command line take precedence over values in a template parameter object or file.A resource group template is a JSON-based model of a resource group for a complex cloud-based service, such as a web portal.
You can use a resource group template to create a resource group or resource group deployment.
The template includes parameter (placeholders) for configurable property values, likes names and sizes.
You can find many templates in the Azure template gallery and you can create your own templates.

If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Example 1: Test a custom template file  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Test-AzureRmResourceGroupDeployment -ResourceGroupName ContosoLabsRG -TemplateFile $home\Documents\Azure\Templates\CustomHostingPlan.json -TemplateParameterFile $home\Documents\Azure\Templates\HostingPlanParms.jsonPS C:>
```

This command tests a custom template file, CustomHostingPlan.json, and a template parameter file, HostingPlanParms.json.
Because the cmdlet does not find any errors, it does not return any output.

### --------------------------  Example 2: Test a template with dynamic parameter values  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Test-AzureRmResourceGroupDeployment -ResourceGroupName ContosoLabsRG -TemplateFile C:\Users\juneb\Documents\Azure\Templates\NewHostingPlan.json -siteName ContosoDev -siteMode Limited -computeMode Shared -siteLocation 'South Central US' -sku Free.
```

This command uses the Test-AzureRmResourceGroupDeployment cmdlet to test a custom template.
Instead of providing the template parameter names, we used the feature that adds the template parameters to command dynamically.

To use the dynamic parameters, type a minus sign (-) to indicate a parameter name and press the TAB key.
The tab-completion feature supplies parameter name.
To cycle through all of the parameter names, press the TAB key repeatedly.
In this case, we used the dynamic parameters to specify all of the parameter names at the command line.In this case, even though the template parameter names and values are correct, the Parameters section in the custom template is missing the hostingPlan parameter that is specified in the Resource section of the template.
The cmdlet detects and reports this error.

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

### -Mode
The deployment mode.

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
Specify the name of the resource group.
This parameter is mandatory.
Wildcards are not permitted.

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
Specifies the path and name of a JSON file of template parameter names and values.
You must specify values for the template parameters, but you can use this parameter, the TemplateParameterObject parameter, or use the parameters that are added to the command dynamically when you specify the template.

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
The parameters and values are case-sensitive.
You must specify values for the template parameters, but you can use this parameter, the TemplateParameterFile parameter, or use the parameters that are added to the command dynamically when you specify the template.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Models.PSResourceManagerError

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

