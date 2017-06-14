---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-ACSFarm

## SYNOPSIS
Changes the settings of the service configuration on an ACS Farm.

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
 [[-SubscriptionId] <String>] [[-Token] <String>] [[-AdminUri] <Uri>] [-SkipCertificateValidation]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-ACSFarm** cmdlet changes the settings of the service configuration on an Azure Consistent Storage (ACS) Farm.

## EXAMPLES

### Example 1: Modify the settings of an existing farm

```
$ResourceGroup = "System"

$Farm = Get-ACSFarm -ResourceGroupName $ResourceGroup

Set-ACSFarm -ResourceGroupName $ResourceGroup -FarmName $Farm.Name -SettingPollingIntervalInSeconds 45
```

The first command stores the value named System in the variable named $ResourceGroup.

The second command uses the [Get-ACSFarm](./Get-ACSFarm.md) cmdlet to get the farm that is contained in the resource group specified in the $ResourceGroup variable. 
The command stores the result in the variable named $Farm.

The third command uses the **Set-ACSFarm** cmdlet to modify the Farm stored in the $Farm variable.


## PARAMETERS

### -AdminUri
Specifies the link, as a URI, to the service administrator.

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

### -FarmName
Specifies the name of the ACS farm that this cmdlet modifies.

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

### -InformationAction
Specifies how this cmdlet responds to an information event.

The acceptable values for this parameter are:

- Continue
- Ignore
- Inquire
- SilentlyContinue
- Stop
- Suspend

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

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

### -ResourceGroupName
Specifies the name of the resource group that contains the ACS farm.

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
Specifies the retention period in days for which deleted accounts are not garbage collected, i.e.
can be recovered.
This can range from 0 to 9999, where zero meaning to delete the storage accounts on the next garbage collection

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

### -SubscriptionId
Specifies the subscription ID.

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

### Microsoft.AzureStack.AzureConsistentStorage.Commands.FarmResponse

## OUTPUTS

### Microsoft.AzureStack.AzureConsistentStorage.Commands.FarmResponse

## NOTES

## RELATED LINKS

[Add-ACSFarm](./Add-ACSFarm.md)

[Get-ACSFarm](./Get-ACSFarm.md)
