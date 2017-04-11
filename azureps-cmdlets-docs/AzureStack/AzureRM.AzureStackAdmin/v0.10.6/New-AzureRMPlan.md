---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-AzureRMPlan

## SYNOPSIS
The New-AzureRmPlan cmdlet creates a new plan composing the various quotas of the resource provider

## SYNTAX

```
New-AzureRMPlan -Name <String> [-DisplayName <String>] -ArmLocation <String> -ResourceGroup <String>
 [-QuotaIds <String[]>] [-SkuIds <String[]>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
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

### -ArmLocation
Specifies the location of the Azurestack resource manager.
The parameter will be deprecated in future

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
Specifies the display name of the plan

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
Specifies the name of the plan

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

### -QuotaIds
Specifies an array of quota ids.
The resource providers create the quotas and provide the quota ids.
The cmdlets for CRUD operations on  quotas are not available yet and will be added in a future release

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
The resource group name under which the plan resource is created

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
An array of SkuIds from the resource provider

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

## OUTPUTS

### Microsoft.AzureStack.Management.Models.AdminPlanModel

## NOTES

## RELATED LINKS

