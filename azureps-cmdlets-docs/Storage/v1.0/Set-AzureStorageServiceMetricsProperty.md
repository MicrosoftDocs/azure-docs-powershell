---
external help file: RMAzure_Storage.xml
online version: 59b6d8fb-70ff-4b9e-b6af-e303e1451dbb
schema: 2.0.0
---

# Set-AzureStorageServiceMetricsProperty
## SYNOPSIS
Modifies metrics properties for the azure_2 Storage service.

## SYNTAX

```
Set-AzureStorageServiceMetricsProperty [-ServiceType] [-MetricsType] [-Context <AzureStorageContext>]
 [-MetricsLevel <MetricsLevel]>] [-PassThru] [-RetentionDays <Int32]>] [-Version <Double]>]
```

## DESCRIPTION
The **Set-AzureStorageServiceMetricsProperty** cmdlet modifies metrics properties for the azure_2 Storage service.

## EXAMPLES

### Example 1: Modify metrics properties for the Blob service
```
C:\PS>Set-AzureStorageServiceMetricsProperty -ServiceType Blob -MetricsType Hour -MetricsLevel Service -PassThru -RetentionDays 10 -Version 1.0
```

This command modifies version 1.0 metrics for blob storage to a level of Service.
azure_2 Storage service metrics retains entries for 10 days.
Because this command specifies the *PassThru* parameter, the command displays the modified metrics properties.

## PARAMETERS

### -Context
Specifies an azure_2 storage context.
To obtain a storage context, use the New-AzureStorageContext cmdlet.

```yaml
Type: AzureStorageContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True(ByValue,ByPropertyName)
Accept wildcard characters: False
```

### -MetricsLevel
Specifies the metrics level that azure_2 Storage uses for the service.
psdx_paramvalues

-- None
-- Service
-- ServiceAndApi

```yaml
Type: MetricsLevel]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetricsType
Specifies a metrics type.
This cmldet sets the azure_2 Storage service metrics type to the value that this parameter specifies.
psdx_paramvalues Hour and Minute.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Hour, Minute

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlets returns the updated metrics properties.
If you do not specify this parameter, this cmdlet does not return a value.

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

### -RetentionDays
Specifies the number of days that the azure_2 Storage service retains metrics information.

```yaml
Type: Int32]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceType
Specifies the storage service type.
This cmdlet modifies the metrics properties for the service type that this parameter specifies.
psdx_paramvalues

-- Blob 
-- Table
-- Queue
-- File

The value of File is not currently supported.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Accepted values: Blob, Table, Queue, File

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of the azure_2 Storage metrics.
The default value is 1.0.

```yaml
Type: Double]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureStorageServiceMetricsProperty](59b6d8fb-70ff-4b9e-b6af-e303e1451dbb)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

