---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-ACSFarm

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

```
Set-ACSFarm [-ResourceGroupName] <String> [-FarmName] <String> [-SettingsPollingIntervalInSecond <Int32>]
 [-HostStyleHttpPort <Int32>] [-HostStyleHttpsPort <Int32>] [-CorsAllowedOriginsList <String>]
 [-DataCenterUriHostSuffixes <String>] [-BandwidthThrottleIsEnabled <Boolean>]
 [-UsageCollectionIntervalInSeconds <Int32>] [-RetentionPeriodForDeletedStorageAccountsInDays <Int32>]
 [-FeedbackRefreshIntervalInSeconds <Int32>] [-NumberOfAccountsToSync <Int32>]
 [-DefaultThrottleProbabilityDecayIntervalInSeconds <Int32>]
 [-GracePeriodForFullThrottlingInRefreshIntervals <Int32>] [-GracePeriodMaxThrottleProbability <Double>]
 [-OverallRequestThresholdInTps <Double>] [-DefaultRequestThresholdInTps <Double>]
 [-MinimumRequestThresholdInTps <Double>] [-ToleranceFactorForTps <Double>]
 [-OverallIngressThresholdInGbps <Double>] [-DefaultIngressThresholdInGbps <Double>]
 [-MinimumIngressThresholdInGbps <Double>] [-ToleranceFactorForIngress <Double>]
 [-OverallIntranetIngressThresholdInGbps <Double>] [-DefaultIntranetIngressThresholdInGbps <Double>]
 [-MinimumIntranetIngressThresholdInGbps <Double>] [-ToleranceFactorForIntranetIngress <Double>]
 [-OverallEgressThresholdInGbps <Double>] [-DefaultEgressThresholdInGbps <Double>]
 [-MinimumEgressThresholdInGbps <Double>] [-ToleranceFactorForEgress <Double>]
 [-OverallIntranetEgressThresholdInGbps <Double>] [-DefaultIntranetEgressThresholdInGbps <Double>]
 [-MinimumIntranetEgressThresholdInGbps <Double>] [-ToleranceFactorForIntranetEgress <Double>]
 [-OverallTotalIngressThresholdInGbps <Double>] [-DefaultTotalIngressThresholdInGbps <Double>]
 [-MinimumTotalIngressThresholdInGbps <Double>] [-ToleranceFactorForTotalIngress <Double>]
 [-OverallTotalEgressThresholdInGbps <Double>] [-DefaultTotalEgressThresholdInGbps <Double>]
 [-MinimumTotalEgressThresholdInGbps <Double>] [-ToleranceFactorForTotalEgress <Double>]
 [[-SubscriptionId] <String>] [[-Token] <String>] [[-AdminUri] <Uri>] [-SkipCertificateValidation] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AdminUri
{{Fill AdminUri Description}}

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BandwidthThrottleIsEnabled
{{Fill BandwidthThrottleIsEnabled Description}}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CorsAllowedOriginsList
{{Fill CorsAllowedOriginsList Description}}

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

### -DataCenterUriHostSuffixes
{{Fill DataCenterUriHostSuffixes Description}}

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

### -DefaultEgressThresholdInGbps
{{Fill DefaultEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultIngressThresholdInGbps
{{Fill DefaultIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultIntranetEgressThresholdInGbps
{{Fill DefaultIntranetEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultIntranetIngressThresholdInGbps
{{Fill DefaultIntranetIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultRequestThresholdInTps
{{Fill DefaultRequestThresholdInTps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultThrottleProbabilityDecayIntervalInSeconds
{{Fill DefaultThrottleProbabilityDecayIntervalInSeconds Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultTotalEgressThresholdInGbps
{{Fill DefaultTotalEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultTotalIngressThresholdInGbps
{{Fill DefaultTotalIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FarmName
{{Fill FarmName Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FeedbackRefreshIntervalInSeconds
{{Fill FeedbackRefreshIntervalInSeconds Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GracePeriodForFullThrottlingInRefreshIntervals
{{Fill GracePeriodForFullThrottlingInRefreshIntervals Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GracePeriodMaxThrottleProbability
{{Fill GracePeriodMaxThrottleProbability Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostStyleHttpPort
{{Fill HostStyleHttpPort Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostStyleHttpsPort
{{Fill HostStyleHttpsPort Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumEgressThresholdInGbps
{{Fill MinimumEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumIngressThresholdInGbps
{{Fill MinimumIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumIntranetEgressThresholdInGbps
{{Fill MinimumIntranetEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumIntranetIngressThresholdInGbps
{{Fill MinimumIntranetIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumRequestThresholdInTps
{{Fill MinimumRequestThresholdInTps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumTotalEgressThresholdInGbps
{{Fill MinimumTotalEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumTotalIngressThresholdInGbps
{{Fill MinimumTotalIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfAccountsToSync
{{Fill NumberOfAccountsToSync Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverallEgressThresholdInGbps
{{Fill OverallEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverallIngressThresholdInGbps
{{Fill OverallIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverallIntranetEgressThresholdInGbps
{{Fill OverallIntranetEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverallIntranetIngressThresholdInGbps
{{Fill OverallIntranetIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverallRequestThresholdInTps
{{Fill OverallRequestThresholdInTps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverallTotalEgressThresholdInGbps
{{Fill OverallTotalEgressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverallTotalIngressThresholdInGbps
{{Fill OverallTotalIngressThresholdInGbps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
{{Fill ResourceGroupName Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionPeriodForDeletedStorageAccountsInDays
{{Fill RetentionPeriodForDeletedStorageAccountsInDays Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsPollingIntervalInSecond
{{Fill SettingsPollingIntervalInSecond Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipCertificateValidation
{{Fill SkipCertificateValidation Description}}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
{{Fill SubscriptionId Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Token
{{Fill Token Description}}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ToleranceFactorForEgress
{{Fill ToleranceFactorForEgress Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToleranceFactorForIngress
{{Fill ToleranceFactorForIngress Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToleranceFactorForIntranetEgress
{{Fill ToleranceFactorForIntranetEgress Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToleranceFactorForIntranetIngress
{{Fill ToleranceFactorForIntranetIngress Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToleranceFactorForTotalEgress
{{Fill ToleranceFactorForTotalEgress Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToleranceFactorForTotalIngress
{{Fill ToleranceFactorForTotalIngress Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToleranceFactorForTps
{{Fill ToleranceFactorForTps Description}}

```yaml
Type: Double
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsageCollectionIntervalInSeconds
{{Fill UsageCollectionIntervalInSeconds Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### System.String
System.Uri

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

