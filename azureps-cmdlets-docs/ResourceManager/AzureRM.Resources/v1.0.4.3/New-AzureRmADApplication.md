---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRmADApplication

## SYNOPSIS
Creates a new azure active directory application.

## SYNTAX

### ApplicationWithoutCredentialParameterSet (Default)
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]>
 [<CommonParameters>]
```

### ApplicationWithPasswordPlainParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]> -Password <String>
 [-StartDate <DateTime>] [-EndDate <DateTime>] [<CommonParameters>]
```

### ApplicationWithPasswordCredentialParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]>
 -PasswordCredentials <PSADPasswordCredential[]> [<CommonParameters>]
```

### ApplicationWithKeyPlainParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]> -KeyValue <String>
 [-KeyType <String>] [-KeyUsage <String>] [-StartDate <DateTime>] [-EndDate <DateTime>] [<CommonParameters>]
```

### ApplicationWithKeyCredentialParameterSet
```
New-AzureRmADApplication -DisplayName <String> -HomePage <String> -IdentifierUris <String[]>
 -KeyCredentials <PSADKeyCredential[]> [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

Creates a new azure active directory application.

## EXAMPLES

### --------------------------  Create new AAD application.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> New-AzureRmADApplication -DisplayName "NewApplication" -HomePage "http://www.microsoft.com" -IdentifierUris "http://NewApplication"
```

Creates a new azure active directory application without any credentials.

Type                    : Application
ApplicationId           : 9400567a-3d4f-4c99-a690-276ba94fbf47
ApplicationObjectId     : 4de22120-3c65-4786-aa51-9886c079d892
AvailableToOtherTenants : False
AppPermissions          : {{
                            "claimValue": "user_impersonation",
                            "description": "Allow the application to access NewApplication on behalf of the signed-in
                          user.",
                            "directAccessGrantTypes": \[\],
                            "displayName": "Access NewApplication",
                            "impersonationAccessGrantTypes": \[
                              {
                                "impersonated": "User",
                                "impersonator": "Application"
                              }
                            \],
                            "isDisabled": false,
                            "origin": "Application",
                            "permissionId": "0efb9772-220f-48d4-9f86-eb3e01402d54",
                            "resourceScopeType": "Personal",
                            "userConsentDescription": "Allow the application to access NewApplication on your behalf.",
                            "userConsentDisplayName": "Access NewApplication",
                            "lang": null
                          }}

### --------------------------  Create new AAD application with password.  --------------------------
@{paragraph=PS C:\\\>}



```
PS C:\> New-AzureRmADApplication -DisplayName "NewApplication" -HomePage "http://www.microsoft.com" -IdentifierUris "http:
//NewApplication" -Password "password"
```

Creates a new azure active directory application and associates password credentials with it.

Type                    : Application
ApplicationId           : a3dad041-8119-4182-b500-f8f959bf31db
ApplicationObjectId     : b4cd1619-80b3-4cfb-9f8f-9f2333425738
AvailableToOtherTenants : False
AppPermissions          : {{
                            "claimValue": "user_impersonation",
                            "description": "Allow the application to access NewApplication on behalf of the signed-in
                          user.",
                            "directAccessGrantTypes": \[\],
                            "displayName": "Access NewApplication",
                            "impersonationAccessGrantTypes": \[
                              {
                                "impersonated": "User",
                                "impersonator": "Application"
                              }
                            \],
                            "isDisabled": false,
                            "origin": "Application",
                            "permissionId": "18509754-f97a-47f9-9c31-d4a16046e0ee",
                            "resourceScopeType": "Personal",
                            "userConsentDescription": "Allow the application to access NewApplication on your behalf.",
                            "userConsentDisplayName": "Access NewApplication",
                            "lang": null
                          }}

## PARAMETERS

### -DisplayName
@{Text=}

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

### -EndDate
@{Text=}

```yaml
Type: DateTime
Parameter Sets: ApplicationWithPasswordPlainParameterSet, ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HomePage
@{Text=}

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

### -IdentifierUris
@{Text=}

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyCredentials
@{Text=}

```yaml
Type: PSADKeyCredential[]
Parameter Sets: ApplicationWithKeyCredentialParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyType
@{Text=}

```yaml
Type: String
Parameter Sets: ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyUsage
@{Text=}

```yaml
Type: String
Parameter Sets: ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyValue
@{Text=}

```yaml
Type: String
Parameter Sets: ApplicationWithKeyPlainParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Password
@{Text=}

```yaml
Type: String
Parameter Sets: ApplicationWithPasswordPlainParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PasswordCredentials
@{Text=}

```yaml
Type: PSADPasswordCredential[]
Parameter Sets: ApplicationWithPasswordCredentialParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartDate
@{Text=}

```yaml
Type: DateTime
Parameter Sets: ApplicationWithPasswordPlainParameterSet, ApplicationWithKeyPlainParameterSet
Aliases: 

Required: False
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
Keywords: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

[Remove-AzureRmADApplication]()

[New-AzureRmADServicePrincipal]()

[Remove-AzureRmADServicePrincipal]()

