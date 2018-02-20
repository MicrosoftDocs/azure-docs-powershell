---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
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
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetSharesForMigration
```
Get-AzsStorageShare -SourceShareName <String> [-Intent <FileShareGetIntent>] [-SkipCertificateValidation]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzsStorageShare** cmdlet gets a list of shares used by the Storage to place storage accounts.

## EXAMPLES

## PARAMETERS

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzsStorageFarm](./Get-AzsStorageFarm.md)

[Get-AzsStorageShareMetric](./Get-AzsStorageShareMetric.md)

[Get-AzsStorageShareMetricDefinition](./Get-AzsStorageShareMetricDefinition.md)

