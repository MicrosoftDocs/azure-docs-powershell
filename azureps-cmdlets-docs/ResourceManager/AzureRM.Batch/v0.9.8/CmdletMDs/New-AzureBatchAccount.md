---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\Get-AzureBatchAccount.md
schema: 2.0.0
---

# New-AzureBatchAccount

## SYNOPSIS
Creates a new Batch account.

## SYNTAX

```
New-AzureBatchAccount [-AccountName] <String> [-Location] <String> [-ResourceGroupName] <String>
 [-Tag <Hashtable[]>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureBatchAccount** cmdlet creates a new Azure Batch account under the specified resource group and location.

## EXAMPLES

### Example 1: Create a new Batch account
```
PS C:\>New-AzureBatchAccount -AccountName "cmdletexample" -ResourceGroupName "CmdletExampleRG" -Location "WestUS"
AccountName          Location        ResourceGroupName Tags               TaskTenantUrl
-----------          --------        ----------------- ----               -------------
cmdletexample       WestUS           CmdletExampleRG                      https://batch.core.contoso.net
```

This command creates a new Batch account named cmdletexample using the CmdletExampleRG resource group in the WestUS location.

## PARAMETERS

### -AccountName
Specifies the name of the Batch account to create.

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

### -Location
Specifies the region where the account will be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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
Specifies the name of the resource group where the account will be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

### BatchAccountContext

## NOTES

## RELATED LINKS

[Get-AzureBatchAccount](.\Get-AzureBatchAccount.md)

[Remove-AzureBatchAccount](.\Remove-AzureBatchAccount.md)

[Set-AzureBatchAccount](.\Set-AzureBatchAccount.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

