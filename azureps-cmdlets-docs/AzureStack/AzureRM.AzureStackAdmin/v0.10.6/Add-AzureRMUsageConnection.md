---
external help file: Microsoft.AzureStack.Commands.dll-Help.xml
online version:
schema: 2.0.0
---

# Add-AzureRMUsageConnection

## SYNOPSIS
Adds usage connection details for a resource provider.

## SYNTAX

```
Add-AzureRMUsageConnection -Name <String> -ResourceGroup <String> -ArmLocation <String>
 -ProviderLocation <String> -ProviderNamespace <String> -UsageStorageConnectionString <String>
 -UsageReportingQueue <String> -UsageReportingTable <String> -ErrorReportingQueue <String>
 -ErrorReportingTable <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [-PipelineVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AzureRMUsageConnection** cmdlet adds usage connection details for a resource provider. The cmdlet gets information about the storage account where the resource provider is storing the usage records and gives this information to the usage service. The usage service will retrieve the usage records periodically based on the storage account information provided.

## EXAMPLES

### Example 1: Add usage connection details for the resource provider in the specified resource group
```
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

# Create storage account if other than DevStorage
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
}

Add-AzureRmUsageConnection @usageConnectionParams
```

This example creates a resource group named "UsageConnectionRG" and adds usage connection details for the resource provider in this resource group.

## PARAMETERS

### -ArmLocation
Specifies the location of the resource manager in the Azure Stack.

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
Specifies the name of the queue that is used for reporting the errors. The usage service would insert records in this queue for any errors generated during its collection process.

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
Specifies the name of the table that is used for reporting the errors. The usage service would insert records in this table for any errors generated during its collection process.

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

### -ProviderLocation
Specifies the location of the resource provider for which the usage connection information is being added.

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
Specifies the namespace of the resource provider for which the usage connection information is being added.

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
Specifies the name of the resource group of the resource provider for which the usage connection information is being added.

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

### -UsageReportingQueue
Specifies the name of the queue in which the added usage meta data is stored. Using this metadata, the usage service will read the data from the usage reporting table.

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
Specifies the name of the table in which usage records are stored.

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
Specifies the storage connection string in which the resource provider usage records are stored.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.AzureStack.Management.Models.UsageConnectionModel

## NOTES

## RELATED LINKS
