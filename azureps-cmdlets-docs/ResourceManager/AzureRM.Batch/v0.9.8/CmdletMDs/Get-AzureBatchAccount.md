---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
online version: .\New-AzureBatchAccount.md
schema: 2.0.0
---

# Get-AzureBatchAccount

## SYNOPSIS
Gets a Batch account under the current subscription.

## SYNTAX

```
Get-AzureBatchAccount [[-AccountName] <String>] [[-ResourceGroupName] <String>] [[-Tag] <Hashtable>]
 [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureBatchAccount** cmdlet gets an Azure Batch account under the current subscription.
You can use the *AccountName* parameter to get a single account, or you can use the *ResourceGroupName* parameter to get accounts under that resource group.

## EXAMPLES

### Example 1: Get a batch account by name
```
PS C:\>Get-AzureBatchAccount -AccountName "pfuller"
AccountName          Location        ResourceGroupName Tags               TaskTenantUrl
-----------          --------        ----------------- ----               -------------
pfuller              westus          CmdletExampleRG                      https://pfuller.westus.batch.azure.com
```

This command gets the batch account named pfuller.

### Example 2: Gets the batch accounts associated with a resource group
```
PS C:\>Get-AzureBatchAccount -ResourceGroupName "CmdletExampleRG"
AccountName          Location        ResourceGroupName Tags               TaskTenantUrl
-----------          --------        ----------------- ----               -------------
cmdletexample        westus          CmdletExampleRG                      https://cmdletexample.westus.batch.azure.com
cmdletexample2       westus          CmdletExampleRG                      https://cmdletexample.westus.batch.azure.com
```

This command gets the batch accounts associated with the CmdletExampleRG resource group.

## PARAMETERS

### -AccountName
Specifies the name of the account.
If you specify an account name, this cmdlet only returns the specified account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
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
Specifies the name of the resource group.
If you specify a resource group, this cmdlet lists the accounts under the specified resource group.

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

### -Tag
Specifies tags in an array of hash tables to set on the account.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

[New-AzureBatchAccount](.\New-AzureBatchAccount.md)

[Remove-AzureBatchAccount](.\Remove-AzureBatchAccount.md)

[Set-AzureBatchAccount](.\Set-AzureBatchAccount.md)

[Azure Batch Cmdlets](.\AzureRM.Batch.md)

