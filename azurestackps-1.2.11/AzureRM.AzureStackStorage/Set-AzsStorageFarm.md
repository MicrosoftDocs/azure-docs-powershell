---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Set-AzsStorageFarm

## SYNOPSIS
Modifies the Storage settings and service configurations for the region or farm.

## SYNTAX

```
Set-AzsStorageFarm [-SettingsPollingIntervalInSecond <Int32>] [-HostStyleHttpPort <Int32>]
 [-HostStyleHttpsPort <Int32>] [-CorsAllowedOriginsList <String>] [-DataCenterUriHostSuffixes <String>]
 [-BandwidthThrottleIsEnabled <Boolean>] [-UsageCollectionIntervalInSeconds <Int32>]
 [-RetentionPeriodForDeletedStorageAccountsInDays <Int32>] [-FeedbackRefreshIntervalInSeconds <Int32>]
 [-NumberOfAccountsToSync <Int32>] [-DefaultThrottleProbabilityDecayIntervalInSeconds <Int32>]
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
 [-SkipCertificateValidation] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzsStorageFarm** cmdlet modifies the Storage settings and service configurations for the region or farm.

## EXAMPLES

### Example 1
```
Set-AzsStorageFarm -RetentionPeriodForDeletedStorageAccountsInDays 15 

$StorageFarm= Get-AzsStorageFarm  

$StorageFarm.Settings.RetentionPeriodForDeletedStorageAccountsInDays
```

## PARAMETERS

### -BandwidthThrottleIsEnabled
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

### -DefaultRequestThresholdInTps
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

### -FeedbackRefreshIntervalInSeconds
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

### -RetentionPeriodForDeletedStorageAccountsInDays
Specifies the retention period in days for which deleted accounts are not garbage collected, i.e.
can be recovered. This can range from 0 to 9999, where zero meaning to delete the storage accounts on the next garbage collection

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
Indicates that the cmdlet does not validate the certificate.

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

### -ToleranceFactorForEgress
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzsStorageFarm](./Get-AzsStorageFarm.md)


