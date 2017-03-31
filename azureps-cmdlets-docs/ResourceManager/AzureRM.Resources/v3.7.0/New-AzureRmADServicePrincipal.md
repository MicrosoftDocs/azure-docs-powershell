---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
ms.assetid: D602F910-B26F-473D-B5B6-C7BDFB0A14CB
online version: 
schema: 2.0.0
---

# New-AzureRmADServicePrincipal

## SYNOPSIS
Creates an Azure Active Directory service principal.

## SYNTAX

### ApplicationWithoutCredentialParameterSet (Default)
```
New-AzureRmADServicePrincipal -ApplicationId <Guid> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### ApplicationWithKeyPlainParameterSet
```
New-AzureRmADServicePrincipal -ApplicationId <Guid> -CertValue <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm]
```

### ApplicationWithPasswordCredentialParameterSet
```
New-AzureRmADServicePrincipal -ApplicationId <Guid> -PasswordCredentials <PSADPasswordCredential[]>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### ApplicationWithKeyCredentialParameterSet
```
New-AzureRmADServicePrincipal -ApplicationId <Guid> -KeyCredentials <PSADKeyCredential[]>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### ApplicationWithPasswordPlainParameterSet
```
New-AzureRmADServicePrincipal -ApplicationId <Guid> -Password <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm]
```

### DisplayNameWithPasswordCredentialParameterSet
```
New-AzureRmADServicePrincipal -DisplayName <String> -PasswordCredentials <PSADPasswordCredential[]>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### DisplayNameWithPasswordPlainParameterSet
```
New-AzureRmADServicePrincipal -DisplayName <String> -Password <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm]
```

### DisplayNameWithKeyCredentialParameterSet
```
New-AzureRmADServicePrincipal -DisplayName <String> -KeyCredentials <PSADKeyCredential[]>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### DisplayNameWithoutCredentialParameterSet
```
New-AzureRmADServicePrincipal -DisplayName <String> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm]
```

### DisplayNameWithKeyPlainParameterSet
```
New-AzureRmADServicePrincipal -DisplayName <String> -CertValue <String> [-StartDate <DateTime>]
 [-EndDate <DateTime>] [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
The **New-AzureRmADServicePrincipal** cmdlet creates an Azure Active Directory service principal.

The cmdlet also implicitly creates an application and sets its properties (if the *ApplicationId* parameter is not provided).
In order to update the application specific parameters, use the [Set-AzureRmADApplication](./Set-AzureRmADApplication.md) cmdlet.

## EXAMPLES

### Example 1: Create an Azure Active Directory service principal by application ID


```
PS C:\> New-AzureRmADServicePrincipal -ApplicationId 34a28ad2-dec4-4a41-bc3b-d22ddf90000e
```

This command creates an Azure Active Directory service principal.

DisplayName                    Type                           ObjectId
-----------                    ----                           --------
DemoApp                        ServicePrincipal               f95b6f5c-fc98-4af0-bb8a-34a14ca1dca1

### Example 2: Create an Azure Active Directory service principal


```
PS C:\> New-AzureRmADServicePrincipal -DisplayName "SPForNoExistingApp"
```

This command creates an Azure Active Directory service principal.
The cmdlet also implicitly creates an application since one is not provided.

DisplayName                    Type                           ObjectId
-----------                    ----                           --------
SPForNoExistingApp             ServicePrincipal               784136ca-3ae2-4fdd-a388-89d993e7c780

## PARAMETERS

### -ApplicationId
Specifies the unique application ID for a service principal in a tenant.
Once created this property cannot be changed.
If an application id is not specified, one will be generated.

```yaml
Type: Guid
Parameter Sets: ApplicationWithoutCredentialParameterSet, ApplicationWithKeyPlainParameterSet, ApplicationWithPasswordCredentialParameterSet, ApplicationWithKeyCredentialParameterSet, ApplicationWithPasswordPlainParameterSet
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

### -Password
Specifies the password to be associated with the service principal.

```yaml
Type: String
Parameter Sets: ApplicationWithPasswordPlainParameterSet, DisplayNameWithPasswordPlainParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDate
Specifies the effective start date of the credential usage.
The default start date value is today. 
For an "asymmetric" type credential, this must be set to on or after the date that the X509 certificate is valid from.

```yaml
Type: DateTime
Parameter Sets: ApplicationWithKeyPlainParameterSet, ApplicationWithPasswordPlainParameterSet, DisplayNameWithPasswordPlainParameterSet, DisplayNameWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndDate
Specifies the effective end date of the credential usage.
The default end date value is one year from today. 
For an "asymmetric" type credential, this must be set to on or before the date that the X509 certificate is valid.

```yaml
Type: DateTime
Parameter Sets: ApplicationWithKeyPlainParameterSet, ApplicationWithPasswordPlainParameterSet, DisplayNameWithPasswordPlainParameterSet, DisplayNameWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PasswordCredentials
Specifies the list of password credentials associated with the service principal.

```yaml
Type: PSADPasswordCredential[]
Parameter Sets: ApplicationWithPasswordCredentialParameterSet, DisplayNameWithPasswordCredentialParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertValue
Specifies the value of the "asymmetric" credential type.
It represents the base 64 encoded certificate.

```yaml
Type: String
Parameter Sets: ApplicationWithKeyPlainParameterSet, DisplayNameWithKeyPlainParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyCredentials
Specifies the list of certificate credentials associated with the service principal.

```yaml
Type: PSADKeyCredential[]
Parameter Sets: ApplicationWithKeyCredentialParameterSet, DisplayNameWithKeyCredentialParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies the friendly name of the service principal.

```yaml
Type: String
Parameter Sets: DisplayNameWithPasswordCredentialParameterSet, DisplayNameWithPasswordPlainParameterSet, DisplayNameWithKeyCredentialParameterSet, DisplayNameWithoutCredentialParameterSet, DisplayNameWithKeyPlainParameterSet
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
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[Get-AzureRmADServicePrincipal]()

[Remove-AzureRmADServicePrincipal](./Remove-AzureRmADServicePrincipal.md)

[New-AzureRmADApplication](./New-AzureRmADApplication.md)

[Remove-AzureRmADApplication](./Remove-AzureRmADApplication.md)

[Get-AzureRmADSpCredential](./Get-AzureRmADSpCredential.md)

[New-AzureRmADSpCredential](./New-AzureRmADSpCredential.md)

[Remove-AzureRmADSpCredential](./Remove-AzureRmADSpCredential.md)
