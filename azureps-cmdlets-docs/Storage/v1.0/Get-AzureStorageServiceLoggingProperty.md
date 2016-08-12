---
external help file: RMAzure_Storage.xml
online version: 671aeec8-b7f9-49c5-866f-da84f189ab5b
schema: 2.0.0
---

# Get-AzureStorageServiceLoggingProperty
## SYNOPSIS
Gets logging properties for azure_2 Storage services.

## SYNTAX

```
Get-AzureStorageServiceLoggingProperty [-ServiceType] [-Context <AzureStorageContext>]
```

## DESCRIPTION
The **Get-AzureStorageServiceLoggingProperty** cmdlet gets logging properties for azure_2 Storage services.

## EXAMPLES

### Example 1: Get logging properties for the Blob service
```
C:\PS>Get-AzureStorageServiceLoggingProperty -ServiceType Blob
```

This command gets logging properties for blob storage.

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

### -ServiceType
Specifies the storage service type.
This cmdlet gets the logging properties for the service type that this parameter specifies.
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

[Set-AzureStorageServiceLoggingProperty](3981e765-b861-4024-a1d2-2c60590ebe0e)

