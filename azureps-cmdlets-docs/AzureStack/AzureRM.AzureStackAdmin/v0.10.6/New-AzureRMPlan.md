---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# New-AzureRMPlan

## SYNOPSIS
Creates a new plan comprising the various quotas of the resource provider.

## SYNTAX

```
New-AzureRMPlan -Name <String> [-DisplayName <String>] -ArmLocation <String> -ResourceGroup <String>
 [-QuotaIds <String[]>] [-SkuIds <String[]>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureRmPlan** cmdlet creates a new plan comprising the various quotas of the resource provider.

## EXAMPLES

### Example 1: Create a plan
```
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
```

This example creates a plan with the display name "ComputePlan" and the quota IDs contained in the $quotaIds variable.

## PARAMETERS

### -ArmLocation
Specifies the location of the Azure stack resource manager in the Azure stack installation.

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
Specifies the display name of the plan.

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
Specifies a variable that is used for storing an informational message.

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
Specifies the name of the plan.

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
Specifies a variable that stores the value of the current pipeline element.

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
Specifies an array of quota IDs. The resource providers create the quotas and provide the IDs.

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
Specifies the name of the resource group under which the plan resource is created.

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
An array of SKU IDs from the resource provider.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.AdminPlanModel

## NOTES

## RELATED LINKS
