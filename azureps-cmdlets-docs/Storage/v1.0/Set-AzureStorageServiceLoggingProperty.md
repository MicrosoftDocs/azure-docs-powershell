---
external help file: RMAzure_Storage.xml
online version: 02217f39-6c93-401b-8801-52fdd38ba751
schema: 2.0.0
---

# Set-AzureStorageServiceLoggingProperty
## SYNOPSIS
Modifies logging for azure_2 Storage services.

## SYNTAX

```
Set-AzureStorageServiceLoggingProperty [-ServiceType] [-Context <AzureStorageContext>]
 [-LoggingOperations <LoggingOperations[]>] [-PassThru] [-RetentionDays <Int32]>] [-Version <Double]>]
```

## DESCRIPTION
The **Set-AzureStorageServiceLoggingProperty** cmdlet modifies logging for azure_2 Storage services.

## EXAMPLES

### Example 1: Modify logging properties for the Blob service
```
C:\PS>Set-AzureStorageServiceLoggingProperty -ServiceType Blob -LoggingOperations Read,Write -PassThru -RetentionDays 10 -Version 1.0
```

This command modifies version 1.0 logging for blob storage to include read and write operations.
azure_2 Storage service logging retains entries for 10 days.
Because this command specifies the *PassThru* parameter, the command displays the modified logging properties.

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

### -LoggingOperations
Specifies an array of azure_2 Storage service operations.
azure_2 Storage services logs the operations that this parameter specifies.
psdx_paramvalues

-- None
-- Read
-- Write
-- Delete
-- All

```yaml
Type: LoggingOperations[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the updated logging properties.
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
Specifies the number of days that the azure_2 Storage service retains logged information.

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
This cmdlet modifies the logging properties for the service type that this parameter specifies.
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
Specifies the version of the azure_2 Storage service logging.
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

[Get-AzureStorageServiceLoggingProperty](02217f39-6c93-401b-8801-52fdd38ba751)

[New-AzureStorageContext](671aeec8-b7f9-49c5-866f-da84f189ab5b)

