---
external help file: Microsoft.AzureStack.AzureConsistentStorage.Commands.dll-Help.xml
Module Name: AzureRM.AzureStackStorage
online version: 
schema: 2.0.0
---

# Get-AzsStorageAcquisition

## SYNOPSIS
Gets or lists page blob acquisitions.

## SYNTAX

```
Get-AzsStorageAcquisition [-TenantSubscriptionId <String>] [-StorageAccountName <String>] [-Container <String>]
 [-SkipCertificateValidation] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzsStorageAcquisition** gets or lists page blob acquisitions.

## EXAMPLES

### Example 1
```
Get-AzsStorageAcquisition -StorageAccountName "teststorage"
```

This command gets the page blob acquisitions for a storage account named teststorage.

## PARAMETERS

### -Container
Specifies the name of the container that contains the acquisition.

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

### -StorageAccountName
Specifies the name of the storage account that contains the acquisition.

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

### -TenantSubscriptionId
Specifies the ID of the tenant subscription.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzsStorageQuota](./[Remove-AzsStorageQuota.md)

