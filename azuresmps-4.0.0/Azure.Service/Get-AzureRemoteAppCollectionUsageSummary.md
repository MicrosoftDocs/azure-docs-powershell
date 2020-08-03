---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 8EF86C66-498F-4183-9070-F178628483F1
online version: 
schema: 2.0.0
---

# Get-AzureRemoteAppCollectionUsageSummary

## SYNOPSIS
Retrieves a usage summary for an Azure RemoteApp collection.

## SYNTAX

```
Get-AzureRemoteAppCollectionUsageSummary [-CollectionName] <String> [[-UsageMonth] <String>]
 [[-UsageYear] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteAppCollectionUsageSummary** cmdlet retrieves a usage summary for an Azure RemoteApp collection.

## EXAMPLES

### Example 1: Get a usage summary
```
PS C:\> Get-AzureRemoteAppCollectionUsageSummary -CollectionName Contoso -UsageMonth 12 -UsageYear 2014
```

This command gets a usage summary for the month of December in the year 2014, for a collection named Contoso.

## PARAMETERS

### -CollectionName
Specifies the name of the Azure RemoteApp collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsageMonth
Specifies a two digit number for the month for which to get a usage summary.
If this parameter is not specified, this cmdlet provides usage for the current month.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsageYear
Specifies the four-digit year for which to get a usage summary.
If this parameter is not specified, this cmdlet provides a usage summary for the current year will be used.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRemoteAppCollection](./Get-AzureRemoteAppCollection.md)

[Get-AzureRemoteAppCollectionUsageDetails](./Get-AzureRemoteAppCollectionUsageDetails.md)


