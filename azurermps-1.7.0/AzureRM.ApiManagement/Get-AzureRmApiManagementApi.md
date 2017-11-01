---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApiManagementApi

## SYNOPSIS
Gets a list or a particular API description.

## SYNTAX

### All APIs (Default)
```
Get-AzureRmApiManagementApi -Context <PsApiManagementContext> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### Find by ID
```
Get-AzureRmApiManagementApi -Context <PsApiManagementContext> -ApiId <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Find by Name
```
Get-AzureRmApiManagementApi -Context <PsApiManagementContext> -Name <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Find by product ID
```
Get-AzureRmApiManagementApi -Context <PsApiManagementContext> -ProductId <String>
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets a list or a particular API description.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementApi -Context $apimContext
```

Get list of all APIs.

### --------------------------  Example 2  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementApi -Context $apimContext -ApiId $apiId
```

Get API by Id.

### --------------------------  Example 3  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementApi -Context $apimContext -Name "EchoApi"
```

Get API by Name

## PARAMETERS

### -ApiId
API identifier to look for.
If specified will try to get the API by the Id.
This parameter is optional.

```yaml
Type: String
Parameter Sets: Find by ID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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
Name of the API.
If specified will try to get the API by name.
This parameter is optional.

```yaml
Type: String
Parameter Sets: Find by Name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProductId
If specified will try to get all Product APIs.
This parameter is optional.

```yaml
Type: String
Parameter Sets: Find by product ID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IList<Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementApi>

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementApi

## NOTES

## RELATED LINKS

