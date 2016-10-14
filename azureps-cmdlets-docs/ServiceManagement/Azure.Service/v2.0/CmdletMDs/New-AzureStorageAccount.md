---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: .\Get-AzureStorageAccount.md
schema: 2.0.0
---

# New-AzureStorageAccount

## SYNOPSIS
Creates a new storage account in an Azure subscription.

## SYNTAX

### ParameterSetAffinityGroup (Default)
```
New-AzureStorageAccount [-StorageAccountName] <String> [-Label <String>] [-Description <String>]
 -AffinityGroup <String> [-Type <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

### ParameterSetLocation
```
New-AzureStorageAccount [-StorageAccountName] <String> [-Label <String>] [-Description <String>]
 -Location <String> [-Type <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzureStorageAccount** cmdlet creates an account that provides access to Azure storage services.
A storage account is a globally unique resource within the storage system.
The account is the parent namespace for the Blob, Queue, and Table services.

## EXAMPLES

### Example 1: Create a storage account for a specified affinity group
```
PS C:\>New-AzureStorageAccount -StorageAccountName "azure01" -Label "AzureOne" -AffinityGroup "prodapps"
```

This command creates a storage account for a specified affinity group.

### Example 1: Create a storage account in a specified location
```
PS C:\>New-AzureStorageAccount -StorageAccountName "azure02" -Label "AzureTwo" -Location "North Central US"
```

This command creates a storage account in a specified location.

## PARAMETERS

### -StorageAccountName
Specifies a name for the storage account.
The storage account name must be unique to Azure and must be between 3 and 24 characters in length and use lowercase letters and numbers only.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Label
Specifies a label for the storage account.
The label may be up to 100 characters in length.

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

### -Description
Specifies a description for the storage account.
The description may be up to 1024 characters in length.

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

### -AffinityGroup
Specifies the name of an existing affinity group in the current subscription.
You can specify either the *Location* or *AffinityGroup* parameter, but not both.

```yaml
Type: String
Parameter Sets: ParameterSetAffinityGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the type of the storage account.
Valid values are:

- Standard_LRS
- Standard_ZRS
- Standard_GRS
- Standard_RAGRS
- Premium_LRS

If this parameter is not specified, the default value is Standard_GRS.

Standard_ZRS or Premium_LRS accounts cannot be changed to other account types, and vice versa.

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

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the Azure data center location where the storage account is created.
You can include either the *Location* or *AffinityGroup* parameter, but not both.

```yaml
Type: String
Parameter Sets: ParameterSetLocation
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

[Get-AzureStorageAccount](.\Get-AzureStorageAccount.md)

[Set-AzureStorageAccount](.\Set-AzureStorageAccount.md)

