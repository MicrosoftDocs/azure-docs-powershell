---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: A0D4D7C9-8783-4837-850F-24F1C9C3A1B1
---

# New-AzureRMTenantSubscription

## SYNOPSIS
Creates a subscription as a tenant for the specified offer.

## SYNTAX

```
New-AzureRMTenantSubscription -OfferId <String> [-DisplayName <String>] [-AdminUri <Uri>] [-Token <String>]
 [-ApiVersion <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

## DESCRIPTION
The **New-AzureRMTenantSubscription** cmdlet creates a subscription as a tenant for the specified offer.

## EXAMPLES

### Example 1:
```
$Offer =  Get-AzureRMOffer -Provider "Default" | Where-Object name -eq "ComputeOffer"
New-AzureRmTenantSubscription  -OfferId $Offer.Id -DisplayName "Compute Subscription"
```
The first command gets all Azure Resource Manager offers that are named ComputeOffer and stores the offers in the variable named $Offer.
The second command creates a subscription for the logged in tenant user using the information stored in the $Offer variable.


## PARAMETERS

### -AdminUri
Specifies the Azure Stack Resource Manager endpoint.
This parameter is not needed if you use the cmdlet against the Azure Stack environment configured against Azure Active Directory.
This parameter will be deprecated in future.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApiVersion
Specifies the supported API version.
This parameter is optional.
This parameter will be deprecated in future.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies the name of the tenant subscription that this cmdlet creates.

```yaml
Type: String
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
* Continue
* Ignore
* Inquire
* SilentlyContinue
* Stop
* Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa
Accepted values: SilentlyContinue, Stop, Continue, Inquire

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

### -OfferId
Specifies the ID of the offer to which the tenant subscribes to create a new subscription.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineVariable
Stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Token
Specifies the authentication token for making the request.
This parameter is not needed if you use the cmdlet against the Azure Stack environment configured against Azure Active Directory.
This parameter will be deprecated in a future release.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Models.SubscriptionDefinition

## NOTES

## RELATED LINKS

[Get-AzureRMTenantSubscription](./Get-AzureRMTenantSubscription.md)

[Remove-AzureRMTenantSubscription](./Remove-AzureRMTenantSubscription.md)

[Set-AzureRMTenantSubscription](./Set-AzureRMTenantSubscription.md)
