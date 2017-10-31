---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzsStorageShare

## SYNOPSIS
Gets a list of shares used by the Storage to place storage accounts.

## SYNTAX

### ListTenant (Default)
```
Get-AzsStorageShare [-ShareName <String>] [-SkipCertificateValidation]
```

### GetSharesForMigration
```
Get-AzsStorageShare -SourceShareName <String> [-Intent <FileShareGetIntent>] [-SkipCertificateValidation]
```

## DESCRIPTION
The **Get-AzsStorageShare** cmdlet gets a list of shares used by the Storage to place storage accounts.

## PARAMETERS

### -Intent
Specifies the intent for returning the shares. The allowed value for this parameter is ContainerMigration.  

```yaml
Type: FileShareGetIntent
Parameter Sets: GetSharesForMigration
Aliases: 
Accepted values: ContainerMigration

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ShareName
Specifies the name of the SMB share.

```yaml
Type: String
Parameter Sets: ListTenant
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -SourceShareName
The share from which the containers will be migrated.

```yaml
Type: String
Parameter Sets: GetSharesForMigration
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## RELATED LINKS

[Get-AzsStorageFarm](./Get-AzsStorageFarm.md)

[Get-AzsStorageShareMetric](./Get-AzsStorageShareMetric.md)

[Get-AzsStorageShareMetricDefinition](./Get-AzsStorageShareMetricDefinition.md)

