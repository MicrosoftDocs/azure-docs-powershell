---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: D0CB99F7-CE58-4E8D-929A-2F5005394CC0
---

# Set-AzureRMResourceProviderRegistration

## SYNOPSIS
Updates the provider registration manifest with the new provider registration model.

## SYNTAX

```
Set-AzureRMResourceProviderRegistration -ProviderRegistration <ProviderRegistrationModel>
 -ResourceGroup <String> [-SubscriptionId <Guid>] [-AdminUri <Uri>] [-Token <String>] [-ApiVersion <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION
The **Set-AzureRMResourceProviderRegistration** cmdlet updates the provider registration manifest with the new provider registration model.

## EXAMPLES

### Example 1:
```
$Manifest = Get-AzureRMResourceProviderRegistration -Name "Microsoft.Compute" -ResourceGroup "system" -Managed; # Modify the manifest object for the need;  Set-AzureRMResourceProviderRegistration -ProviderRegistration $Manifest -ResourceGroup "System"
```

This command gets the Provider Registration object named Microsoft.Compute and then updates the changes.

## PARAMETERS

### -AdminUri
Specifies the Azure Stack Resource Manager endpoint.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured with Azure Active Directory.
This parameter will be deprecated in the future.

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
This parameter will be deprecated in the future.

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

### -ProviderRegistration
Specifies the provider Registration Model object.
You can get the object through the [Get-AzureRmResourceProviderRegistration](./Get-AzureRmResourceProviderRegistration.md) cmdlet and modify the values needed.

```yaml
Type: ProviderRegistrationModel
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroup
Specifies the name of the resource group that contains the provider registration.

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
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured with Azure Active Directory.
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

### Microsoft.AzureStack.Management.Models.ProviderRegistrationModel

## NOTES

## RELATED LINKS

[Add-AzureRMResourceProviderRegistration](./Add-AzureRMResourceProviderRegistration.md)

[Get-AzureRMResourceProviderRegistration](./Get-AzureRMResourceProviderRegistration.md)

[Remove-AzureRMResourceProviderRegistration](./Remove-AzureRMResourceProviderRegistration.md)
