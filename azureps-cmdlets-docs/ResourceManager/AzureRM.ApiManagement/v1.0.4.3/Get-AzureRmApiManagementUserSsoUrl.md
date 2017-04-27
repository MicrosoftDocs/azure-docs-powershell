---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApiManagementUserSsoUrl

## SYNOPSIS
Generates SSO URL for the user.

## SYNTAX

```
Get-AzureRmApiManagementUserSsoUrl -Context <PsApiManagementContext> -UserId <String>
```

## DESCRIPTION
Generates SSO URL for the user.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}

```
Get-AzureRmApiManagementUserSsoUrl -Context $apimContext -UserId 0123456789
```

Get user SSO URL.

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

### -UserId
Identifier of existing user.
This parameter is required.

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

## INPUTS

## OUTPUTS

### string

## NOTES
Keywords: azure, azurerm, arm, resource, management, manager, api, apimanagement, apimgmt, apism

## RELATED LINKS

