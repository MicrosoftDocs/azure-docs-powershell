---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DA25F968-DBC9-48BB-9FF7-0BDBE1D4571C
---

# Set-AzureRMResourceProviderRegistration

## SYNOPSIS
Updates the provider registration manifest with the new provider registration model

## SYNTAX

```
Set-AzureRMResourceProviderRegistration -ProviderRegistration <ProviderRegistrationModel>
 -ResourceGroup <String> [-SubscriptionId <Guid>] [-AdminUri <Uri>] [-Token <String>] [-ApiVersion <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$manifest = Get-AzureRMResourceProviderRegistration -Name "Microsoft.Compute" -ResourceGroup "system" -Managed; # Modify the manifest object for the need;  Set-AzureRMResourceProviderRegistration -ProviderRegistration $manifest -ResourceGroup "System"
```

Description

-----------

The example shows how to get the Provider Registration object and then update for the changes

## PARAMETERS

### -AdminUri
Specifies the azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory.
This parameter will be deprecated in future

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
Specifies the api version supported.
This parameter will be deprecated in future

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

### -ProviderRegistration
Provider Registration Model object.
Get the object through Get-AzureRmResourceProviderRegistration and modify the values needed

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
Resource group name

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

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Models.ProviderRegistrationModel

## NOTES
## RELATED LINKS

