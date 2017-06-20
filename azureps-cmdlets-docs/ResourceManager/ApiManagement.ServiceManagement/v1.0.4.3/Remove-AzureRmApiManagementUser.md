---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-AzureRmApiManagementUser

## SYNOPSIS
Deletes a user.

## SYNTAX

```
Remove-AzureRmApiManagementUser -Context <PsApiManagementContext> -UserId <String> [-DeleteSubscriptions]
 [-PassThru] [-Force] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureRmApiManagementUser** cmdlet deletes a user.

## EXAMPLES

### Example 1: Delete a user without confirmation
```
PS C:\> Remove-AzureRmApiManagementUser -Context $apimContext -UserId "0123456789" -Force
```

This command deletes the user identified by the ID "0123456789".

## PARAMETERS

### -Context
Specifies an **PsApiManagementContext** object that contains details about the context of the Azure API Management service.

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

### -DeleteSubscriptions
Indicates whether to delete the user's subscriptions to products.
If this parameter is not included and subscriptions exist, an exception will be thrown.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Indicates whether to run this command without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies whether to return an object representing the item removed.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserId
Specifies the ID of the user to remove.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
### System.String

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Get-AzureRmApiManagementUser](./Get-AzureRmApiManagementUser.md)

[New-AzureRmApiManagementUser](./New-AzureRmApiManagementUser.md)

[Set-AzureRmApiManagementUser](./Set-AzureRmApiManagementUser.md)
