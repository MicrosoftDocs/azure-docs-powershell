---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackAdmin
online version: 
schema: 2.0.0
---

# New-AzsPlan

## SYNOPSIS
Creates a new plan comprising different resource provider quotas. 

## SYNTAX

```
New-AzsPlan -Name <String> [-DisplayName <String>] -ArmLocation <String> -ResourceGroupName <String>
 [-QuotaIds <String[]>] [-SkuIds <String[]>] [-DefaultProfile <IAzureContextContainer>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-PipelineVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The New-AzsPlan cmdlet creates a new plan composing the various quotas of the resource provider.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
$quotaIds = @()
$computeQuota = New-ComputeQuota -QuotaName "Basic" -Location "local"
$quotaIds += $computeQuota.Id
# Add other resource provider quotas if needed

New-AzsPlan -Name $PlanName -DisplayName "ComputePlan" -ArmLocation "local" -ResourceGroupName $ResourceGroupName -QuotaIds $quotaIds


function New-ComputeQuota
{
param
(
[parameter(Mandatory=$true)]
[string] $QuotaName,

[parameter(Mandatory=$true)]
[string] $Location,

[int] $VirtualMachineCount = 2,

[int] $MemoryLimitMB = 2048,

[int] $CoresLimit = 2,

[string] $ApiVersion = "2015-12-01-preview"
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

Description

-----------

The following example creates a plan. Note that quota creation cmdlets are not available yet and will be added in a future release

## PARAMETERS

### -ArmLocation
Specifies the location of the Azurestack resource manager.
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

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
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
Specifies how this cmdlet responds to an information event. The following values are permitted for this object type.

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
Specifies an array of quota ids.
The resource providers create the quotas and provide the quota ids.
The cmdlets for CRUD operations on  quotas are not available yet and will be added in a future release.

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

### -ResourceGroupName
The resource group name under which the plan resource is created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ResourceGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuIds
An array of SkuIds from the resource provider.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

