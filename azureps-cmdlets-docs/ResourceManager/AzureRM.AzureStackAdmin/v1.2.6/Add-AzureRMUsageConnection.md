---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
ms.assetid: E83CB5A9-088F-4748-947E-16705B6BA5B7
---

# Add-AzureRMUsageConnection

## SYNOPSIS
Adds an usage connection details for a resource provider.

## SYNTAX

```
Add-AzureRMUsageConnection -Name <String> -ResourceGroup <String> [-SubscriptionId <Guid>]
 -ArmLocation <String> -ProviderLocation <String> -ProviderNamespace <String>
 -UsageStorageConnectionString <String> -UsageReportingQueue <String> -UsageReportingTable <String>
 -ErrorReportingQueue <String> -ErrorReportingTable <String> [-AdminUri <Uri>] [-Token <String>]
 [-ApiVersion <String>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>]
```

## DESCRIPTION
The **Add-AzureRMUsageConnection** cmdlet adds an usage connection details for a resource provider.
The cmdlet gets the storage account information where the resource provider is storing the usage records.
This information is given to the usage service through this cmdlet.
Usage Service will retrieve the usage records periodically from the storage account information provided.

## EXAMPLES

### Example 1:
```
Add-AzureRmUsageConnection @usageConnectionParams
```

The following example registers a usage connection information of a resource provider to usage service.

            $usageConnectionId = "sqlrpusageconnection"
            $location = "local"

            # Create Resource Group
            # The following name could be anything
            $usageConnectionRG="UsageConnectionRG"
            New-AzureRMResourceGroup -Name $usageConnectionRG  -Location $location -Force

            # Make sure the tables and queues exist
            # if not create them with New-AzureStorageTale/New-AzureStorageQueue
            $usageReportingQueue = "sqlrpusagequeue"
            $usageReportingTable = "sqlrpusagetable"
            $errorReportingQueue = "sqlrpusageerrorqueue"
            $errorReportingTable = "sqlrpusageerrortable"

            # Create Storage Account If Other than DevStorage
            $storageConnectionString = "UseDevelopmentStorage=true"


            $usageConnectionParams = @{
            Name = $usageConnectionId
            ResourceGroup = $usageConnectionRG
            ProviderNamespace = "Microsoft.Sql"
            ArmLocation = $location
            ProviderLocation = $location
            UsageStorageConnectionString = $storageConnectionString
            UsageReportingQueue = $usageReportingQueue
            UsageReportingTable = $usageReportingTable
            ErrorReportingQueue = $errorReportingQueue
            ErrorReportingTable = $errorReportingTable
            ApiVersion = "2015-06-01-preview"
            }

            Add-AzureRmUsageConnection @usageConnectionParams

## PARAMETERS

### -AdminUri
Specifies the azure stack resource manager endpoint.
This parameter is not needed when using the cmdlet against the azure stack environment configured against Azure active directory

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
API Version for the usage connection API.
You need to set this to 2015-06-01-preview.
This parameter will get removed in a future release.

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
Specifies the location of the resource manager instance in the Azure Stack installation.

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

### -ErrorReportingQueue
Specifies the queue name for reporting the errors.
Usage service would insert records in this queue for any errors during its collection process.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ErrorReportingTable
Specifies the table name for reporting the errors.
Usage service would insert records in this queue for any errors during its collection process.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies the name of the usage connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ProviderLocation
Specifies the location of the resource provider for which this cmdlet adds the usage connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProviderNamespace
Specifies the namespace of the resource provider for which this cmdlet adds the usage connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Specifies the resource group name for the usage connection resource.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
Specifeis the service administrator subscription ID.
This parameter is not needed when using the cmdlet against the azure stack environment configured against Azure active directory.
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
This parameter is not needed when using the cmdlet against the Azure stack environment configured against Azure active directory.
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

### -UsageReportingQueue
Specifies the queue name where the added usage meta data is queued.
Using this metadata, Usage service will read the data from reporting table for usage aggregation.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UsageReportingTable
Specifies the table name where this cmdlet inserts usage records.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UsageStorageConnectionString
Specifies the storage connection string in which this cmdlet inserts the resource provider usage records.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Models.UsageConnectionModel

## NOTES

## RELATED LINKS

[Get-AzureRMUsageConnection.md](./Get-AzureRMUsageConnection.md)

[Remove-AzureRMUsageConnection.md](./Remove-AzureRMUsageConnection.md)
