---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: B16535FA-887D-475C-A925-CA9346CBFC91
---

# Add-AzureRMResourceProviderRegistration

## SYNOPSIS
Adds a resource provider manifest to Azure stack resource manager.

## SYNTAX

### MultipleExtensions (Default)
```
Add-AzureRMResourceProviderRegistration -Name <String> -Namespace <String> -ResourceGroup <String>
 -ArmLocation <String> -DisplayName <String> [-SubscriptionId <Guid>] -ProviderLocation <String>
 [-Extensions <String>] -ResourceTypes <String> [-AdminUri <Uri>] [-Token <String>] [-ApiVersion <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
```

### SingleExtension
```
Add-AzureRMResourceProviderRegistration -Name <String> -Namespace <String> -ResourceGroup <String>
 -ArmLocation <String> -DisplayName <String> [-SubscriptionId <Guid>] -ProviderLocation <String>
 -ExtensionName <String> -ExtensionUri <Uri> -ResourceTypes <String> [-AdminUri <Uri>] [-Token <String>]
 [-ApiVersion <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

## DESCRIPTION
The **Add-AzureRMResourceProviderRegistration** cmdlet adds a resource provider manifest to Azure stack resource manager.
This is needed to register any new resource provider with resource manager.

## EXAMPLES

### Example 1: Register the resource provider manifest for the specified namespace
```
# Make sure to provide the resource types json of the resource provider being registered
$AdminResourceTypesFile="$PSScriptRoot\AdminResourceTypes.json"
$AdminNamespace="Microsoft.Sql.Admin"
$AdminJson = Get-Content $AdminResourceTypesFile -Raw | ConvertFrom-Json
$AdminJson | % { $_.endpoints\[0\].endpointUri="https://${VmName}:30010" }
$AdminJsonStr = $AdminJson | ConvertTo-Json -Depth 4

$Location = "local"
Add-AzureRMResourceProviderRegistration -Name $AdminNamespace \`
-Namespace $AdminNamespace \`
-ResourceGroup System \`
-ArmLocation $Location \`
-ProviderLocation $Location \`
-DisplayName $AdminNamespace \`
-ExtensionName "SqlAdminExtension" \`
-ExtensionUri "https://${VmName}:13002"  \`
-ResourceTypes $AdminJsonStr

```

The following example registers the resource provider manifest for a namespace providing the details needed.            

## PARAMETERS

### -AdminUri
Specifies the Azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the Azure stack environment configured against Azure active directory.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApiVersion
Specifies API Version for the usage connection api.
This needs to be 2015-06-01-preview.
This parameter will get removed in a future release.

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

### -DisplayName
@{Text=}

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

### -ExtensionName
Specifies the extension name associated with the resource provider manifest.

```yaml
Type: String
Parameter Sets: SingleExtension
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Extensions
Specifies a JSON string that contains the extension names and extension URIs associated with the resource provider manifest.
This parameter is used only when there are multiple parameters associated with a single resource provider manifest.

```yaml
Type: String
Parameter Sets: MultipleExtensions
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionUri
Specifies the extension URI associated with the resource provider manifest.

```yaml
Type: Uri
Parameter Sets: SingleExtension
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:
* Continue
* Ignore
* Inquire
* SilentlyContinue
* Stop
* Suspend


```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa
Accepted values: SilentlyContinue, Stop, Continue, Inquire

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Specifies an information variable.

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

### -Name
Specifies the resource provider manifest name.

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

### -Namespace
Specifies the namespace associated with the resource provider manifest.

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

### -PipelineVariable
Stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderLocation
Specifies the location of the resource provider.

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

### -ResourceGroup
Specifies the resource group under which the cmdlet creates the resource provider manifest.

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

### -ResourceTypes
Specifies a JSON string that describes the resource provider manifest.

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

### -SubscriptionId
Specifies the service administrator subscription ID.
This parameter is not needed when you use the cmdlet against the Azure stack environment configured against Azure active directory.
This parameter will be deprecated in a future release.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Token
Specifies the authentication token for which the cmdlet makes the request.
This parameter is not needed when using the cmdlet against the Azure stack environment configured against Azure active directory.
This parameter will be deprecated in a future release.

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

### -ArmLocation
Specifies the location of the Azure Stack Resource Manager.
This parameter will be deprecated in a future release.

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

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Models.ProviderRegistrationModel

## NOTES
## RELATED LINKS

[Get-AzureRMResourceProviderRegistration](./Get-AzureRMResourceProviderRegistration.md)

[Remove-AzureRMResourceProviderRegistration](./Remove-AzureRMResourceProviderRegistration.md)

[Set-AzureRMResourceProviderRegistration](./Set-AzureRMResourceProviderRegistration.md)
