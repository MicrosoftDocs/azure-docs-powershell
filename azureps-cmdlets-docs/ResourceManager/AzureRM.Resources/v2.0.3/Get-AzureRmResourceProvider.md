---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=393044
schema: 2.0.0
---

# Get-AzureRmResourceProvider

## SYNOPSIS

## SYNTAX

### ListAvailable (Default)
```
Get-AzureRmResourceProvider [-Location <String>] [-ListAvailable] [-ApiVersion <String>] [-Pre]
 [<CommonParameters>]
```

### IndividualProvider
```
Get-AzureRmResourceProvider -ProviderNamespace <String> [-Location <String>] [-ApiVersion <String>] [-Pre]
 [<CommonParameters>]
```

## DESCRIPTION
If you find an issue with this cmdlet, please create an issue on https://github.com/Azure/azure-powershell/issues, with a lable "ResourceManager".

## EXAMPLES

### --------------------------  Example 1: Get all registered resource providers --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceProvider
```

This command gets all the registered resource providers.

### --------------------------  Example 2: Get all resource providers, including those not registered --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceProvider -ListAvailable
```

This command gets all the resource providers, including those registered and unregistered.

### --------------------------  Example 3: Get details about a particular resource provider --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceProvider -ProviderNamespace Microsoft.Web
```

This command gets details about a particular resource provider, including the resource types and locations available for the resource provider.

### --------------------------  Example 4: Get all registered resource providers filtered by a location --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\>Get-AzureRmResourceProvider -Location westus
```

This command gets all the registered resource providers under a location.

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

### -ListAvailable
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: ListAvailable
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
The location to look for provider namespace.

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

### -ProviderNamespace
@{Text=}

```yaml
Type: String
Parameter Sets: IndividualProvider
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

## OUTPUTS

## NOTES

## RELATED LINKS

