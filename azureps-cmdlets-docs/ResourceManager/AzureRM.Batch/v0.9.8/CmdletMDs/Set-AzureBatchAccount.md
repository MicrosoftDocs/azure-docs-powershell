---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccount.md
schema: 2.0.0
---

# Set-AzureBatchAccount

## SYNOPSIS
Updates the specified Batch account.

## SYNTAX

```
Set-AzureBatchAccount [-AccountName] <String> [-Tag] <Hashtable[]> [-ResourceGroupName <String>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureBatchAccount** cmdlet updates the specified Azure Batch account.
Currently, only tags can be updated.

## EXAMPLES

### Example 1: Update the tags on an existing Batch account
```
PS C:\>Set-AzureBatchAccount -AccountName "cmdletexample" -Tag @(@{Name = "tag1";Value = "value1"},@{Name = "tag2";Value = "value2"})
AccountName          Location        ResourceGroupName Tags               TaskTenantUrl
-----------          --------        ----------------- ----               -------------
cmdletexample        westus          cmdletexamplerg   {System.Collection https://cmdletexample.westus.batch.azure.com
                                                       s.Hashtable, Syste
                                                       m.Collections.Hash
                                                       table}
```

This command updates the tags on the cmdletexample account.

## PARAMETERS

### -AccountName
Specifies the name of the existing Batch account to update.

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
Specifies the resource group of the account being updated.

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

### -Tag
Specifies tags in an array of hash tables to set on the account.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: Tags

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### BatchAccountContext

## NOTES

## RELATED LINKS

[Get-AzureBatchAccount](.\Get-AzureBatchAccount.md)

[New-AzureBatchAccount](.\New-AzureBatchAccount.md)

[Remove-AzureBatchAccount](.\Remove-AzureBatchAccount.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

