---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-AzureRmApiManagementSubscription

## SYNOPSIS
Gets one or more subscriptions.

## SYNTAX

### Get all subscriptions (Default)
```
Get-AzureRmApiManagementSubscription -Context <PsApiManagementContext> [<CommonParameters>]
```

### Get by subsctiption ID
```
Get-AzureRmApiManagementSubscription -Context <PsApiManagementContext> [-SubscriptionId <String>]
 [<CommonParameters>]
```

### Get by user ID
```
Get-AzureRmApiManagementSubscription -Context <PsApiManagementContext> [-UserId <String>] [<CommonParameters>]
```

### Get by product ID
```
Get-AzureRmApiManagementSubscription -Context <PsApiManagementContext> [-ProductId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmApiManagementSubscription** cmdlet gets a specified subscription, or all subscriptions, if no subscription is specified.

## EXAMPLES

### Example 1: Get all subscriptions
```
PS C:\> Get-AzureRmApiManagementSubscription -Context $apimContext
```

This command gets all subscriptions.

### Example 2: Get a specific subscription
```
PS C:\> Get-AzureRmApiManagementSubscription -Context $apimContext -SubscriptionId "0123456789"
```

This command gets the subscription that is identified by the ID "0123456789".

### Example 3: Get all subscriptions for a user
```
PS C:\> Get-AzureRmApiManagementSubscription -Context $apimContext -UserId "777"
```

This command gets all of a user's subscriptions.

### Example 4: Get all subscriptions to a product
```
PS C:\> Get-AzureRmApiManagementSubscription -Context $apimContext -ProductId "999"
```

This command gets all subscriptions to the product identified by the ID "999".

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

### -ProductId
Specifies the ID of a product.
If this parameter is included, the cmdlet gets all subscriptions to the product.

```yaml
Type: String
Parameter Sets: Get by product ID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
Specifies the ID of a subscription to get.
If this parameter is included, the cmdlet gets the subscription that has the specified ID.

```yaml
Type: String
Parameter Sets: Get by subsctiption ID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserId
Specifies the ID of a user.
If this parameter is included, the cmdlet gets all subscriptions for the user.

```yaml
Type: String
Parameter Sets: Get by user ID
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

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

## OUTPUTS

### System.Collections.Generic.IList

## NOTES

## RELATED LINKS

[New-AzureRmApiManagementSubscription](./New-AzureRmApiManagementSubscription.md)

[Remove-AzureRmApiManagementSubscription](./Remove-AzureRmApiManagementSubscription.md)

[Set-AzureRmApiManagementSubscription](./Set-AzureRmApiManagementSubscription.md)
