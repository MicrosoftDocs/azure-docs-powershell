---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 7B8C8239-16A3-4C47-9D6F-DE31885532F4
online version: 
schema: 2.0.0
---

# Set-AzureRmADServicePrincipal

## SYNOPSIS
Updates an existing Azure Active Directory service principal.

## SYNTAX

### SpObjectIdWithDisplayNameParameterSet (Default)
```
Set-AzureRmADServicePrincipal -ObjectId <String> -DisplayName <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### SPNWithDisplayNameParameterSet
```
Set-AzureRmADServicePrincipal -ServicePrincipalName <String> -DisplayName <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The **Set-AzureRmADServicePrincipal** cmdlet updates an existing Azure Active Directory service principal. 
To update the credentials associated with this service principal, use the [New-AzureRmADSpCredential](./New-AzureRmADSpCredential.md) cmdlet. 
To update the properties associated with the underlying application, use the [Set-AzureRmADApplication](./Set-AzureRmADApplication.md) cmdlet.

## EXAMPLES

### Example 1: Update the display name for the specified service principal by object ID

```
PS C:\> Set-AzureRmADServicePrincipal -ObjectId 784136ca-3ae2-4fdd-a388-89d793e7c780 -DisplayName "UpdatedNameForSp"
```

This command updates the display name for the service principal with specified object ID.

### Example 2: Update the display name for the specified service principal by name

```
PS C:\> Set-AzureRmADServicePrincipal -ServicePrincipalName "http://MyApp1" -DisplayName "UpdatedNameforSp"
```

This command updates the display name for the service principal with specified service principal name.

## PARAMETERS

### -ObjectId
Specifies the object id of the service principal that this cmdlet updates.

```yaml
Type: String
Parameter Sets: SpObjectIdWithDisplayNameParameterSet
Aliases: ServicePrincipalObjectId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies the new display name for the service principal.

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

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicePrincipalName
Specifies the Service Principal Name (SPN) of service principal that this cmdlet updates.

```yaml
Type: String
Parameter Sets: SPNWithDisplayNameParameterSet
Aliases: SPN

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmADServicePrincipal](./Get-AzureRmADServicePrincipal.md)

[New-AzureRmADServicePrincipal](./New-AzureRmADServicePrincipal.md)

[Remove-AzureRmADServicePrincipal](./Remove-AzureRmADServicePrincipal.md)

[Set-AzureRmADApplication](./Set-AzureRmADApplication.md)

[New-AzureRmADSpCredential](./New-AzureRmADSpCredential.md)

[Remove-AzureRmADSpCredential](./Remove-AzureRmADSpCredential.md)
