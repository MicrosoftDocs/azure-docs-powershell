---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Add-AzureRMResourceProviderRegistration

## SYNOPSIS
This cmdlet adds a resource provider manifest to azure stack resource manager.
This is needed to register any new resource provider with resource manager.

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

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```

```

Description

-----------

The following example registers the resource provider manifest for a namespace providing the details needed


            # Make sure to provide the resource types json of the resource provider being registered
            $adminResourceTypesFile="$PSScriptRoot\AdminResourceTypes.json"
            $adminNamespace="Microsoft.Sql.Admin"
            $adminJson = Get-Content $adminResourceTypesFile -Raw | ConvertFrom-Json
            $adminJson | % { $_.endpoints\[0\].endpointUri="https://${VmName}:30010" }
            $adminJsonStr = $adminJson | ConvertTo-Json -Depth 4

            $location = "local"
            Add-AzureRMResourceProviderRegistration -Name $adminNamespace \`
            -Namespace $adminNamespace \`
            -ResourceGroup System \`
            -ArmLocation $location \`
            -ProviderLocation $location \`
            -DisplayName $adminNamespace \`
            -ExtensionName "SqlAdminExtension" \`
            -ExtensionUri "https://${VmName}:13002"  \`
            -ResourceTypes $adminJsonStr

## PARAMETERS

### -AdminUri
Specifies the azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory

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
This needs to be '2015-06-01-preview' .
Note that this parameter will get removed in a future release

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
Extension name associated with the resource provider manifest

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
Json string specifying the extension names and extension URIs associated with the resource provider manifest.
This parameter is used only when there are multiple parameters associated with a single resource provider manifest

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
Extension URI associated with the resource provider manifest

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
Not Specified

The following values are permitted for this object type.

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
Not Specified

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
Resource provider manifest name

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
Namespace associated with the resource provider manifest

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
Not Specified

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
Location of the resource provider

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
Resource group under which the resource provider manifest is created

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
Json string describing the resource provider manifest.

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
Service administrator subscription id.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory. 
This parameter will be deprecated in a future release

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
Authentication token for making the request.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory. 
This parameter will be deprecated in a future release

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
{{Fill ArmLocation Description}}

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

