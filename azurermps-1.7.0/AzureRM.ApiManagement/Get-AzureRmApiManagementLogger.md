---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmApiManagementLogger

## SYNOPSIS
Gets the details of the Logger.

## SYNTAX

### Get all loggers (Default)
```
Get-AzureRmApiManagementLogger -Context <PsApiManagementContext> [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### Get by logger ID
```
Get-AzureRmApiManagementLogger -Context <PsApiManagementContext> [-LoggerId <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets the details of the Logger.

## EXAMPLES

### --------------------------  Example 1  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementLogger -Context $apimContext
```

Gets a List of all the Loggers.

### --------------------------  Example 2  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmApiManagementLogger -Context $apimContext -LoggerId 123
```

Gets a Logger by LoggerId.

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

### -LoggerId
Identifier of a logger.
If specified will try to find logger by the identifier.
This parameter is optional.

```yaml
Type: String
Parameter Sets: Get by logger ID
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

### IList<Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementLogger>

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementLogger.PsApiManagementLogger

## NOTES

## RELATED LINKS

