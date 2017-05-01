---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApiManagementOpenIdConnectProvider

## SYNOPSIS
Gets the details of the OpenID Connect Provider.

## SYNTAX

### Get all OpenID Connect Providers (Default)
```
Get-AzureRmApiManagementOpenIdConnectProvider -Context <PsApiManagementContext>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Get by OpenID Connect Provider ID
```
Get-AzureRmApiManagementOpenIdConnectProvider -Context <PsApiManagementContext>
 [-OpenIdConnectProviderId <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### Find by OpenID Connect Provider friendly Name
```
Get-AzureRmApiManagementOpenIdConnectProvider -Context <PsApiManagementContext> [-Name <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets the details of the OpenID Connect Provider.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementOpenIdConnectProvider -Context $apimContext
```

Gets details of all OpenID Connect Providers.

### --------------------------  Example 2  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementOpenIdConnectProvider -Context $apimContext -OpenIdConnectProviderId $openIdConnectProviderId
```

Gets the details of the OpenID connect Provider by Identifier

### --------------------------  Example 3  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementOpenIdConnectProvider -Context $apimContext -Name $openIdConnectProviderName
```

Gets the OpenID Connect Provider by Friendly Name.

## PARAMETERS

### -Context
Instance of PsApiManagementContext.
This parameter is required.

```yaml
Type: PsApiManagementContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
@{Text=}

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
@{Text=}

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
OpenID Connect Provider friendly name.
If specified will try to find openID Connect Provider by the name.
This parameter is optional.

```yaml
Type: String
Parameter Sets: Find by OpenID Connect Provider friendly Name
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OpenIdConnectProviderId
Identifier of a OpenID Connect Provider.
If specified will try to find openId Connect Provider by the identifier.
This parameter is optional.

```yaml
Type: String
Parameter Sets: Get by OpenID Connect Provider ID
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

### IList<Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementOpenIdConnectProvider>

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementLogger.PsApiManagementOpenIdConnectProvider

## NOTES

## RELATED LINKS

