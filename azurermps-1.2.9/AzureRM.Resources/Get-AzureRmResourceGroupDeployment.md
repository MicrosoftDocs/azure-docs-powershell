---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393044
schema: 2.0.0
---

# Get-AzureRmResourceGroupDeployment

## SYNOPSIS
Gets the deployments in a resource group.

## SYNTAX

### The deployment name parameter set. (Default)
```
Get-AzureRmResourceGroupDeployment [-ResourceGroupName] <String> [[-Name] <String>] [<CommonParameters>]
```

### The deployment Id parameter set.
```
Get-AzureRmResourceGroupDeployment -Id <String> [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmResourceGroupDeployment cmdlet gets the deployments in an Azure resource group.
You can use the Name (DeploymentName) and ProvisioningState parameters to filter the deployments.
By default, Get-AzureRmResourceGroupDeployment returns all deployments for a specified resource group.An Azure resource is a user-managed Azure entity, such as a database server, database, or web site.
An Azure resource group is a collection of Azure resources that are deployed as a unit.
A deployment is the operation that makes the resources in the resource group available for use.This cmdlet is very useful for tracking.
For debugging, use it with the Get-AzureRmResourceGroupLog cmdlet.

## EXAMPLES

### --------------------------  Example 1: Get all deployments for a resource group  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroupDeployment -ResourceGroupName ContosoLabsRG
DeploymentName    : WordPress.WordPress
ResourceGroupName : ContosoLabsRG
ProvisioningState : Succeeded
Timestamp         : 3/26/2014 1:56:55 AM
Mode              : Incremental
TemplateLink      : 
                    Uri            : https://gallerystoreprodch.blob.core.windows.net/prod-microsoft-windowsazure-gallery/8D6B920B-10F4-4B5A-B3DA-9D398FBCF3EE.PUBLICGALLERYITEMS.WORDPRESS.WORDPRESS.0.1.0-PREVIEW1/Deplo                  ymentTemplates/Website_NewHostingPlanBasicStandard_MySQL_NewDB.json
                    ContentVersion : 1.0.0.0


Parameters        : 
                    Name             Type                       Value
                    ===============  =========================  ==========
                    siteName         String                     wordpress-group-ws01
                    hostingPlanName  String                     Plan
                    siteMode         String                     Limited
                    computeMode      String                     Dedicated
                    siteLocation     String                     North Europe
                    sku              String                     Standard
                    workerSize       String                     0
                    databaseName     String                     wordpressgroupdbwp1
                    databaseLocation  String                    North Europe
                    databaseSku      String
                    subscriptionId   String                     c9cbd920-c00c-427c-852b-8aaf38babcde
                    resourceGroup    String                     ContosoLabsRG
                    dbSubscriptionId  String                    c9cbd920-c00c-427c-852b-8aaf38babcde
                    dbResourceGroup  String                     WordPress-Group
                    autoscaleEnabled  Bool                      True
Outputs           :
```

This command gets all deployments for the ContosoLabsRG resource group.
The output shows a deployment for a WordPress blog that used a gallery template.

### --------------------------  Example 2: Get a deployment by name  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroupDeployment -ResourceGroupName ContosoLabsRG -Name DeployWebsite1
```

This command gets the DeployWebsite1 deployment of the ContosoLabsRG resource group.
You can assign a name to a deployment when you create it by using the New-AzureRmResourceGroup or New-AzureRmResourceGroupDeployment cmdlets.
If you do not assign a name, the cmdlets provide a default name based on the template used to create the deployment.

### --------------------------  Example 4: Get the deployments of all resource groups  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceGroup | Get-AzureRmResourceGroupDeployment | Format-Table ResourceGroupName, DeploymentName, ProvisioningState
ResourceGroupName                   DeploymentName                          ProvisioningState
-----------------                   --------------                          -----------------
ContosoAppa001                      Microsoft.WebSiteSQLDatabase.0.1.0-p... Succeeded
ContosoAppa001                      DBUpdated                               Canceled
DevTest001                          CakeSoftwareFoundation.CakePHP.0.1.0... Succeeded
LabDeploy001                        Ghost.Ghost.0.1.0-preview1              Succeeded
ContosoDB                           CLrg001depl001                          Succeeded
ContosoBlog                         WordPress.WordPress.0.1.0-preview1      Succeeded
ContosoLabsRG                       WordPress.WordPress                     Succeeded
```

This command gets all deployments of all resource groups in the subscription and formats them in a table with their ResourceGroupName, DeploymentName and ProvisioningState property values.

## PARAMETERS

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
Gets only the deployment with the specified name.
Wildcards are not permitted.
This parameter is optional.
By default, Get-AzureRmResourceGroupDeployment returns all deployments for the specified resource group.

```yaml
Type: String
Parameter Sets: The deployment name parameter set.
Aliases: DeploymentName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Gets the deployments for the specified resource group.
Wildcards are not permitted.
This parameter is required and you can specify only one resource group in each command.

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

### Microsoft.Azure.Commands.ResourceManagement.Models. PSResourceGroupDeployment

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

