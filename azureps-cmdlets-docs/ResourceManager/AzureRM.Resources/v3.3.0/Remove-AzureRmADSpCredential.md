---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: 04B1E3A6-6D52-46A3-8241-2CCDB5E71642
online version: 
schema: 2.0.0
---

# Remove-AzureRmADSpCredential

## SYNOPSIS
Removes a credential from a service principal.

## SYNTAX

### ObjectIdWithKeyIdParameterSet (Default)
```
Remove-AzureRmADSpCredential -ObjectId <String> -KeyId <Guid> [-Force] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### ObjectIdWithAllParameterSet
```
Remove-AzureRmADSpCredential -ObjectId <String> [-All] [-Force] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### SPNWithAllParameterSet
```
Remove-AzureRmADSpCredential -ServicePrincipalName <String> [-All] [-Force]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### SPNWithKeyIdParameterSet
```
Remove-AzureRmADSpCredential -ServicePrincipalName <String> -KeyId <Guid> [-Force]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The **Remove-AzureRmADSpCredential** cmdlet removes a credential key from a service principal in the case of a compromise or as part of credential key rollover expiration.
The service principal is identified by supplying either the object ID or service principal name (SPN).

The credential to be removed is identified by its key ID if an individual credential is to be removed or with an 'All' switch to delete all credentials associated with the service principal.

## EXAMPLES

### Example 1: Remove a credential key from a service principal

```
PS C:\> Remove-AzureRmADSpCredential -ObjectId 7663d3fb-6f86-4352-9e6d-cf9d50d5ee82 -KeyId 9044423a-60a3-45ac-9ab1-09534157ebb
```

This command removes a credential key from a service principal.
In this example, the key with Id "9044423a-60a3-45ac-9ab1-09534157ebb" will be removed from the service principal.

### Example 2: Remove all credential keys from a service principal

```
PS C:\> Remove-AzureRmADSpCredential -ServicePrincipalName http://test123 -All
```

This command removes a credential key from a service principal.
In this example, all credentials will be removed from the service principal associated with the service principal name "http://test123".

## PARAMETERS

### -ObjectId
Specifies the object ID of the service principal that this cmdlet removes the credentials from.

```yaml
Type: String
Parameter Sets: ObjectIdWithKeyIdParameterSet, ObjectIdWithAllParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyId
Specifies the credential key to be removed.
The key Ids for a service principal can be obtained using the [Get-AzureRmADSpCredential](./Get-AzureRmADSpCredential.md) cmdlet.

```yaml
Type: Guid
Parameter Sets: ObjectIdWithKeyIdParameterSet, SPNWithKeyIdParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -All
Indicates that this cmdlet removes all the credentials associated with the service principal.

```yaml
Type: SwitchParameter
Parameter Sets: ObjectIdWithAllParameterSet, SPNWithAllParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServicePrincipalName
Specifies the name of the service principal that this cmdlet removes the credentials from.

```yaml
Type: String
Parameter Sets: SPNWithAllParameterSet, SPNWithKeyIdParameterSet
Aliases: 

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

[Get-AzureRmADSpCredential](./Get-AzureRmADSpCredential.md)

[New-AzureRmADSpCredential](./New-AzureRmADSpCredential.md)

[Get-AzureRmADServicePrincipal](./Get-AzureRmADServicePrincipal.md)
