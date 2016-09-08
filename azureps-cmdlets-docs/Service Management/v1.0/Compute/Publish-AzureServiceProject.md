---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Publish-AzureServiceProject
## SYNOPSIS
Publish the current service to Windows Azure.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Publish-AzureServiceProject [[-ServiceName] <String>] [-AffinityGroup <String>] [-DeploymentName <String>]
 [-ForceUpgrade] [-Launch] [-Location <String>] [-Slot <String>] [-StorageAccountName <String>]
```

### UNNAMED_PARAMETER_SET_2
```
Publish-AzureServiceProject [[-Package] <String>] [-Configuration] <String> [-AffinityGroup <String>]
 [-DeploymentName <String>] [-ForceUpgrade] [-Launch] [-Location <String>] [-Slot <String>]
 [-StorageAccountName <String>]
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Publish-AzureServiceProject cmdlet publishes the current service to the cloud.
You can specify publishing configuration (such as Subscription, StorageAccountName, Location, Slot) on the command line, or in local settings through the Set-AzureServiceProject cmdlet.

## EXAMPLES

### 1: Publish a service project with default values
```
PS C:\>Publish-AzureServiceProject
```

This example publishes the current service, using the current service settings and the current Azure publish profile.

### 2: Create a deployment package
```
PS C:\>Publish-AzureServiceProject -PackageOnly
```

Creates a deployment package (.cspkg) file in the service directory and does not publish to Windows Azure.

## PARAMETERS

### -AffinityGroup
Specifies the affinity group that you want the service to use.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ag

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Configuration
Specifies the service configuration file.
If you specify this parameter, specify the Package parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: cc

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeploymentName
Specifies the deployment name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: dn

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceUpgrade
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -Launch
Opens a browser window so you can view the application after it is deployed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ln

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Location
The region in which the application will be hosted.
Possible values are: Anywhere Asia, Anywhere Europe, Anywhere US, East Asia, East US, North Central US, North Europe, South Central US, Southeast Asia, West Europe, West US. 
If no Location is specified, the location specified in the last call to Set-AzureServiceProject will be used. 
If no Location was ever specified, the Location will be randomly chosen from 'North Central US' and 'South Central US' locations.

```yaml
Type: String
Parameter Sets: (All)
Aliases: l

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Package
Specifies the package file to deploy.
Specify either a local file that has the .cspkg file name extension or a URI of a blob that contains the package.
If you specify this parameter, do not specify the ServiceName parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: sp

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name to be used for the service when publishing to Windows Azure.
The name determines part of the label in the cloudapp.net subdomain that is used to address the service when hosted in Windows Azure (that is, name.cloudapp.net).
Any name specified while publishing the service overrides the name given when the service was created.
(See the New-AzureServiceProject cmdlet).

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: sv

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
The deployment slot to be used for this service.
Possible values are 'Staging' and 'Production'.
If no slot is specified, the slot provided in the last call to Set-AzureDeploymentSlot is used.
If no slot has ever been specified, the 'Production' slot is used.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sl

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the Windows Azure storage account name to be used while publishing the service.
This value is not used until the service is published.
When this parameter is not specified, the value is obtained from the last Set-AzureServiceProject command.
If no storage account was ever specified, a storage account matching the name of the service will be used.
If no such storage account exists, the cmdlet attempts to create a new one.
However, the attempt may fail if a storage account matching the service name exists in another subscription.

```yaml
Type: String
Parameter Sets: (All)
Aliases: st

Required: False
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AzureServiceProjectRemoteDesktop](8d3f7f43-f8f6-4ecf-b8be-7c69cd10cde7)

[Set-AzureServiceProject](c3baa783-e57a-46bd-abe4-6d06130eaaf0)

