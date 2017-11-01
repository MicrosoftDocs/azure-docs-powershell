---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393045
schema: 2.0.0
---

# New-AzureRmResourceGroupDeployment

## SYNOPSIS
Add an Azure deployment to a resource group.

## SYNTAX

### Default (Default)
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] [<CommonParameters>]
```

### Deployment via template file and template parameters object
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateParameterObject <Hashtable> -TemplateFile <String> [<CommonParameters>]
```

### Deployment via template uri and template parameters object
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateParameterObject <Hashtable> -TemplateUri <String> [<CommonParameters>]
```

### Deployment via template file and template parameters file
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateParameterFile <String> -TemplateFile <String> [<CommonParameters>]
```

### Deployment via template uri and template parameters file
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateParameterFile <String> -TemplateUri <String> [<CommonParameters>]
```

### Deployment via template file template parameters uri
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateParameterUri <String> -TemplateFile <String> [<CommonParameters>]
```

### Deployment via template uri and template parameters uri
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateParameterUri <String> -TemplateUri <String> [<CommonParameters>]
```

### Deployment via template file without parameters
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateFile <String> [<CommonParameters>]
```

### Deployment via template uri without parameters
```
New-AzureRmResourceGroupDeployment [-Name <String>] -ResourceGroupName <String> [-Mode <DeploymentMode>]
 [-Force] -TemplateUri <String> [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The New-AzureRmResourceGroupDeployment cmdlet adds a deployment to an existing resource group, including the resources that the deployment requires.
This cmdlet is similar to the New-AzureRmResourceGroup cmdlet, but it works on existing resource groups, instead of new ones.
To add resources to a resource group without using a template, use the New-AzureRmResource cmdlet.An Azure resource is a user-managed Azure entity, such as a database server, database, website, virtual machine, or storage account.
An Azure resource group is a collection of Azure resources that are deployed as a unit, such as the web site, database server, and databases that are required for a financial web site.
A deployment uses a resource group template to add resource to a resource group and publish them so they are available in Azure.To add a resource group deployment, specify the name of an existing resource group and a resource group template, which is a JSON string that represents of a resource group for a complex cloud-based service, such as a web portal.
The template includes parameter (placeholders) for required resources and configurable property values, likes names and sizes.
You can find many templates in the Azure template gallery and you can create your own templates.To find a gallery template, use the Get-AzureRmResourceGroupGalleryTemplate template cmdlet.
To use a gallery template, use the GalleryTemplateIdentity parameter of New-AzureRmResourceGroupDeployment to specify the template identity.
Or, use the Save-AzureRmResourceGalleryTemplate cmdlet to save the gallery template as a JSON file, and then use the TemplateFile or TemplateUri parameters to provide the name and location of the file.You can also create a custom resource group template, either by typing in a text file  or by editing a gallery template.
To use a custom template to create a resource group, use TemplateFile or TemplateUri parameters to supply the location and file name.Each template has different parameters for configurable properties.
To specify values for the template parameters, use a JSON-formatted parameter file (TemplateParameterFile parameter) or a hash table of parameter names and values (TemplateParameterObject parameter).
Or, use the template parameters that are added to the command dynamically as soon as you specify a template.
To use the dynamic parameters, just type them in the command, or type a minus sign to indicate a parameter name (-) and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required parameter, the cmdlet prompts you for the value.
Template parameter values that are typed at the command line take precedence over values in a template parameter object or file.

## EXAMPLES

### --------------------------  Example 1: Use a custom template and parameter file  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>New-AzureRmResourceGroupDeployment -ResourceGroupName ContosoEngineering -TemplateFile D:\Azure\Templates\EngineeringSite.json -TemplateParameterFile D:\Azure\Templates\EngSiteParms.json -TemplateVersion "2.1"
```

This command creates a new deployment by using a custom template and a template file on disk.
The command uses the TemplateFile parameter to specify the template and the TemplateParameterFile to specify a file of parameters and parameter values.
It uses the TemplateVersion parameter to specify a particular version of the template.

## PARAMETERS

### -Force
Do not ask for confirmation.

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
This can be a custom template or a gallery template that is saved to disk as a JSON file, such as by using the Save-AzureRmResourceGroupGalleryTemplate cmdlet.To use this parameter, the subscription must include a storage account where the cmdlet can save the template.
By default, this cmdlet uses the current storage account in the subscription, but you can use the StorageAccountName parameter to specify an alternate storage account.
If you do not specify a storage account and the subscription does not have a storage account that is designated as "current," the command fails.To create a storage account, use the Switch-AzureMode cmdlet to switch to the Azure module, and then use the New-AzureRmStorageAccount cmdlet.
To make the a storage account the "current storage account" for the subscription, use the CurrentStorageAccountName parameter of the Set-AzureRmSubscription cmdlet.

```yaml
Type: String
Parameter Sets: Deployment via template file and template parameters object, Deployment via template file and template parameters file, Deployment via template file template parameters uri, Deployment via template file without parameters
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
Parameter Sets: Deployment via template file and template parameters file, Deployment via template uri and template parameters file
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
Parameter Sets: Deployment via template file and template parameters object, Deployment via template uri and template parameters object
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
Parameter Sets: Deployment via template file template parameters uri, Deployment via template uri and template parameters uri
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TemplateUri
Specifies the URI of a JSON template file.
This file can be a custom template or a gallery template that is saved as a JSON file, such as by using the Save-AzureRmResourceGroupGalleryTemplate cmdlet.

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

### Microsoft.Azure.Commands.ResourceManager.Models.PSResourceGroupDeployment

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

