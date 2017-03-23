---
external help file: Microsoft.Azure.Commands.Management.Storage.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmStorageAccount

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### UpdateAccountType (Default)
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Type] <String> [<CommonParameters>]
```

### UpdateCustomDomain
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-CustomDomainName] <String>
 [[-UseSubDomain] <Boolean>] [<CommonParameters>]
```

### UpdateTags
```
Set-AzureRmStorageAccount [-ResourceGroupName] <String> [-Name] <String> [-Tags] <Hashtable[]>
 [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -CustomDomainName
Storage Account Custom Domain StorageAccountName.

```yaml
Type: String
Parameter Sets: UpdateCustomDomain
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Storage Account StorageAccountName.

```yaml
Type: String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Resource Group StorageAccountName.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tags
Storage Account Tags.

```yaml
Type: Hashtable[]
Parameter Sets: UpdateTags
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Storage Account Type.

```yaml
Type: String
Parameter Sets: UpdateAccountType
Aliases: 
Accepted values: Standard_LRS, Standard_ZRS, Standard_GRS, Standard_RAGRS, Premium_LRS

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSubDomain
To Use Sub Domain StorageAccountName.

```yaml
Type: Boolean
Parameter Sets: UpdateCustomDomain
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

### System.String
System.Nullable`1[[System.Boolean, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089]]
System.Collections.Hashtable[]

## OUTPUTS

### Microsoft.Azure.Management.Storage.Models.StorageAccount

## NOTES

## RELATED LINKS

