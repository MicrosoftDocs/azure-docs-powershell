---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 1449385B-0CFB-455E-B3B7-42D8DCA44BF7
---

# Get-AzureRMPlan

## SYNOPSIS
Gets the plan details.

## SYNTAX

### TenantList (Default)
```
Get-AzureRMPlan [-AdminUri <Uri>] [-Token <String>] [-ApiVersion <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
```

### Admin
```
Get-AzureRMPlan [-Name <String>] -ResourceGroup <String> [-SubscriptionId <Guid>] [-Managed] [-AdminUri <Uri>]
 [-Token <String>] [-ApiVersion <String>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>]
```

### TenantGet
```
Get-AzureRMPlan -Name <String> [-AdminUri <Uri>] [-Token <String>] [-ApiVersion <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>]
```

## DESCRIPTION
The **Get-AzureRmPlan** cmdlet gets the plan details.

## EXAMPLES

### Example 1:
```
Get-AzureRMPlan -Name "ComputePlan" -ResourceGroup "PlanGroup" -Managed
```

The command gets the plan named ComputePlan from the resource group named PlanGroup.

## PARAMETERS

### -AdminUri
Specifies the Azure Stack resource manager endpoint.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured against Azure Active Directory.

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

### -Managed
Indicates that the cmdlet executes the operation as an administrator.

```yaml
Type: SwitchParameter
Parameter Sets: Admin
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the plan.

```yaml
Type: String
Parameter Sets: Admin
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: TenantGet
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

### -ResourceGroup
Specifies the resource group name.

```yaml
Type: String
Parameter Sets: Admin
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Specifies the service administrator subscription ID.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured against Azure Active Directory.
This parameter will be deprecated in a future release.

```yaml
Type: Guid
Parameter Sets: Admin
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Token
Specifies the authentication token for making the request.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured against Azure Active Directory.
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

### Microsoft.AzureStack.Management.Models.AdminPlanModel

## NOTES

## RELATED LINKS

[New-AzureRMPlan](./New-AzureRMPlan.md)

[Remove-AzureRMPlan](./Remove-AzureRMPlan.md)

[Set-AzureRMPlan](./Set-AzureRMPlan.md)
