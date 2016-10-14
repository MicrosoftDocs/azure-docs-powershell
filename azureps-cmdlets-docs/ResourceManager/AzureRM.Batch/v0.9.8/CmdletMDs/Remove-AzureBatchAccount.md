---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccount.md
schema: 2.0.0
---

# Remove-AzureBatchAccount

## SYNOPSIS
Removes the specified  Batch account.

## SYNTAX

```
Remove-AzureBatchAccount [-AccountName] <String> [[-ResourceGroupName] <String>] [-Force]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AzureBatchAccount** cmdlet removes the specified Azure Batch account.
You will be prompted for confirmation unless you use the *Force* parameter.

## EXAMPLES

### Example 1: Remove a batch account by name
```
PS C:\>Remove-AzureBatchAccount -AccountName "cmdletexample"
```

This command removes the batch account named cmdletexample.
The user is prompted for confirmation before the delete operation takes place.

## PARAMETERS

### -AccountName
Specifies the name of the batch account to remove.

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

### -Force
Forces the command to run without asking for user confirmation.

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
Specifies the resource group of the account to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

[Get-AzureBatchAccount](.\Get-AzureBatchAccount.md)

[New-AzureBatchAccount](.\New-AzureBatchAccount.md)

[Set-AzureBatchAccount](.\Set-AzureBatchAccount.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

