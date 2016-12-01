---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: D30CC47A-FE6D-43A8-8602-26CCF145438F
---

# Remove-AzureRMResourceProviderRegistration

## SYNOPSIS
Removes the resource provider manifest.

## SYNTAX

```
Remove-AzureRMResourceProviderRegistration -Name <String> -ResourceGroup <String> [-SubscriptionId <Guid>]
 [-AdminUri <Uri>] [-Token <String>] [-ApiVersion <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION
The **Remove-ResourceProviderRegistration** cmdlet removes the resource provider manifest.

## EXAMPLES

### Example 1: Remove a resource provider manifest
```
Remove-ResourceProviderRegistration -Name "Microsoft.Sql.Admin" -ResourceGroup system
```

This command removes the resource provider manifest for the namespace named Microsoft.Sql.Admin.

## PARAMETERS

### -AdminUri
Specifies the Azure Stack resource manager endpoint.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured with Azure Active Directory.
This parameter will be deprecated in future.

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
Specifies the supported API version.
This parameter is optional.
This parameter will be deprecated in future.

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
Specifies the name of the Azure Resource Manager provider registration that this cmdlet removes.

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

### -ResourceGroup
Specifies the resource group that the contains the Azure Resource Manager provider registration.

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

### -SubscriptionId
Specifies the service administrator subscription ID.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured with Azure Active Directory.
This parameter will be deprecated in a future release.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Token
Specifies the authentication token for making the request.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured with Azure Active Directory.
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

## INPUTS

## OUTPUTS

### Microsoft.Azure.AzureOperationResponse

## NOTES

## RELATED LINKS

[Add-AzureRMResourceProviderRegistration](./Add-AzureRMResourceProviderRegistration.md)

[Get-AzureRMResourceProviderRegistration](./Get-AzureRMResourceProviderRegistration.md)

[Set-AzureRMResourceProviderRegistration](./Set-AzureRMResourceProviderRegistration.md)
