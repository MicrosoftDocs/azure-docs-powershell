---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRMOffer

## SYNOPSIS
The New-AzureRmOffer cmdlet creates an offer composing of the specified base plans and add ons

## SYNTAX

```
New-AzureRMOffer -Name <String> [-DisplayName <String>] [-State <AccessibilityState>]
 [-AddOnPlans <AddonPlanDefinition[]>] [-BasePlanIds <String[]>] -ArmLocation <String> -ResourceGroup <String>
 [-SubscriptionId <Guid>] [-AdminUri <Uri>] [-Token <String>] [-ApiVersion <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
New-AzureRMOffer -Name "ComputePlan" -DisplayName "ComputePlan" -State Private -BasePlanIds $BasePlanIds -ArmLocation "local"-ResourceGroup "OfferGroup"
```

Description

-----------

The example creates an offer with the provided base plans

## PARAMETERS

### -AddOnPlans
An array of AddOn Plan Ids.
The offer will support the extra quotas provided by the AddOns

```yaml
Type: AddonPlanDefinition[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AdminUri
Specifies the azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory.
This parameter will be deprecated in future

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
Specifies the api version supported.
This is optional.
This parameter will be deprecated in future

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

### -ArmLocation
Specifies the location of the Azurestack Resource Manager.
This parameter will be deprecated in a future release

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

### -BasePlanIds
An array of the base plan Ids.
The offer is going to compose of all the base plans and associated quotas

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DisplayName
@{Text=}

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
Not Specified

The following values are permitted for this object type.

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
Not Specified

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
Specifies the name of the offer

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
Not Specified

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

### -ResourceGroup
The existing resource group name where the offer resource is created

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

### -State
Specifies the state of the plan.
The state could be Private, Public or Decommissioned

```yaml
Type: AccessibilityState
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Service administrator subscription id.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory. 
This parameter will be deprecated in a future release

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Token
Authentication token for making the request.
This parameter is not needed when using the cmdlet against the azure stack environment configured against azure active directory. 
This parameter will be deprecated in a future release

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

### Microsoft.AzureStack.Management.Models.AdminOfferModel

## NOTES
## RELATED LINKS

