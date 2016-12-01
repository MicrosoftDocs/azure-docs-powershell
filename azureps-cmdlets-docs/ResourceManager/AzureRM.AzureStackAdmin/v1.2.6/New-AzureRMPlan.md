---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: 9E26F02B-04B7-429E-930D-42D5D71D5044
---

# New-AzureRMPlan

## SYNOPSIS
Creates a plan composing the various quotas of the resource provider.

## SYNTAX

```
New-AzureRMPlan -Name <String> [-DisplayName <String>] -ArmLocation <String> -ResourceGroup <String>
 [-SubscriptionId <Guid>] [-QuotaIds <String[]>] [-SkuIds <String[]>] [-AdminUri <Uri>] [-Token <String>]
 [-ApiVersion <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

## DESCRIPTION
The **New-AzureRmPlan** cmdlet creates a plan composing the various quotas of the resource provider.

## EXAMPLES

### Example 1:
```
New-AzureRMPlan -Name $PlanName -DisplayName "ComputePlan" -ArmLocation "local" -ResourceGroup $ResourceGroupName -QuotaIds $quotaIds
```

Description

-----------

The following example creates a plan.
Note that quota creation cmdlets are not available yet and will be added in a future release

            $quotaIds = @()
            $computeQuota = New-ComputeQuota -QuotaName "Basic" -Location "local"
            $quotaIds += $computeQuota.Id
            # Add other resource provider quotas if needed

            New-AzureRMPlan -Name $PlanName -DisplayName "ComputePlan" -ArmLocation "local" -ResourceGroup $ResourceGroupName -QuotaIds $quotaIds


            function New-ComputeQuota
            {
            param
            (
            \[parameter(Mandatory=$true)\]
            \[string\] $QuotaName,

            \[parameter(Mandatory=$true)\]
            \[string\] $Location,

            \[int\] $VirtualMachineCount = 2,

            \[int\] $MemoryLimitMB = 2048,

            \[int\] $CoresLimit = 2,

            \[string\] $ApiVersion = "2015-12-01-preview"
            )

            Write-Verbose "Creating compute quota named $QuotaName"

            $uri = "{0}subscriptions/{1}/providers/Microsoft.Compute.Admin/locations/{2}/quotas/{3}?api-version={4}" -f $AdminUri, $SubscriptionId, $Location, $QuotaName, $ApiVersion

            $RequestBody = @"
            {
            "name":"$quotaName",
            "type":"Microsoft.Compute.Admin/quotas",
            "location":"$Location",
            "properties":{
            "virtualMachineCount":$VirtualMachineCount,
            "memoryLimitMB":$MemoryLimitMB,
            "coresLimit":$CoresLimit
            }
            }
            "@

            # Get the $Token with Get-AzureStackToken cmdlet
            $headers = @{ "Authorization" = "Bearer "+ $Token }

            $quota = Invoke-RestMethod -Method Put -Uri $uri -Body $RequestBody -ContentType 'application/json' -Headers $headers

            Write-Output $quota
            }

## PARAMETERS

### -AdminUri
Specifies the azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the Azure Stack environment configured against Azure Active Directory.
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

### -ArmLocation
Specifies the location of the Azure Stack Resource Manager.
The parameter will be deprecated in future.

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

### -DisplayName
Specifies the display name of the Azure Stack Resource Manager plan.

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

### -Name
Specifies the name of the plan that this cmdlet creates.

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

### -QuotaIds
Specifies an array of quota IDs.
The resource providers create the quotas and provide the quota IDs.
The cmdlets for CRUD operations on quotas are not available yet and will be added in a future release

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Specifies the resource group name under which the plan resource is created.

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

### -SkuIds
Specifies an array of Sku IDs from the resource provider.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
Specifies the service administrator subscription ID.
This parameter is not needed when you use the cmdlet against the Azure Stack environment configured against Azure Active Directory.
This parameter will be deprecated in a future release.

```yaml
Type: Guid
Parameter Sets: (All)
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
[Get-AzureRMPlan](./Get-AzureRMPlan.md)

[Remove-AzureRMPlan](./Remove-AzureRMPlan.md)

[Set-AzureRMPlan](./Set-AzureRMPlan.md)
