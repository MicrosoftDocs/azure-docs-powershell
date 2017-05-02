---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-AzureRMResourceProviderRegistration

## SYNOPSIS
Updates the provider registration manifest with the new provider registration model.

## SYNTAX

```
Set-AzureRMResourceProviderRegistration -ProviderRegistration <ProviderRegistrationModel>
 -ResourceGroup <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureRMResourceProviderRegistration** cmdlet updates the provider registration manifest with the new provider registration model.

## EXAMPLES

### Example 1: Change a property of a provider registration manifest
```
$manifestToUpdate = Get-AzureRMResourceProviderRegistration -Name "Microsoft.Compute" -ResourceGroup "system" -Managed
$manifestToUpdate.DisplayName = "Compute Registration"
Set-AzureRMResourceProviderRegistration -ProviderRegistration $manifestToUpdate -ResourceGroup "System"
```

This example modifies the **DisplayName** property of the provider registration manifest named "Microsoft.Compute" in the "system" resource group.
The first statement gets the provider registration manifest and stores the object in the $manifestToUpdate variable.
After the **DisplayName** property is changed, the updated object is passed in the **ProviderRegistration** parameter of the **Set-AzureRMResourceProviderRegistration** cmdlet.

## PARAMETERS

### -InformationAction
Specifies how this cmdlet responds to an information event.

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
Specifies a variable that is used for storing an informational message.

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
Specifies a variable that stores the value of the current pipeline element.

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
Specifies an updated **ProviderRegistrationModel** object to be used for updating the existing provider registration data.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.ProviderRegistrationModel

## NOTES

## RELATED LINKS
