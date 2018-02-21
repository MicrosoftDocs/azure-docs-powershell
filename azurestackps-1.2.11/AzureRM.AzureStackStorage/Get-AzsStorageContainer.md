---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Get-AzsStorageContainer

## SYNOPSIS
Gets a list of containers in a share that the system considers as best candidates for migration.

## SYNTAX

```
Get-AzsStorageContainer -ShareName <String> [-Intent <ContainerGetIntent>] [-Count <UInt32>]
 [-StartIndex <UInt32>] [-SkipCertificateValidation] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzsStorageContainer** cmdlet Gets a list of containers in a share that the system considers as best candidates for migration.

## EXAMPLES

### Example 1
```
$shares = Get-AzsStorageShare

Get-AzsStorageContainer -ShareName $shares.ShareName
```

## PARAMETERS

### -Count
Specifies the number of containers to return.

```yaml
Type: UInt32
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

### -Intent
Specifies the intent for returning the storage containers. By default, this value is set to Migration.  

```yaml
Type: ContainerGetIntent
Parameter Sets: (All)
Aliases: 
Accepted values: Migration

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShareName
Specifies the name of the share used in the Azure Consistent Storage system.

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

### -StartIndex
```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

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

[Get-AzsStorageContainerMigrationStatus](./Get-AzsStorageContainerMigrationStatus.md)
