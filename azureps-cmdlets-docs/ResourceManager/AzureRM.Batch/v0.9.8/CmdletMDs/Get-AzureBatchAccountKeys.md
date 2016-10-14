---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\New-AzureBatchAccountKey.md
schema: 2.0.0
---

# Get-AzureBatchAccountKeys

## SYNOPSIS
Gets the specified key of the specified Batch accounts under the current subscription.

## SYNTAX

```
Get-AzureBatchAccountKeys [-AccountName] <String> [-ResourceGroupName <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureBatchAccountKeys** cmdlet gets the specified key of the specified Azure Batch accounts under the current subscription.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AccountName
Specifies the name of the account.
If you specify an account name, this cmdlet only returns the specified account.

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
Type: AzureProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group where the account is created.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureBatchAccountKey](.\New-AzureBatchAccountKey.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

