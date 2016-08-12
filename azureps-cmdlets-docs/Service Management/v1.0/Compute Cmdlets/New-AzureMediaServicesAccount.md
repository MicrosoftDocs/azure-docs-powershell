---
external help file: SMAzure_Compute.xml
online version: http://go.microsoft.com/fwlink/?LinkId=324179
schema: 2.0.0
---

# New-AzureMediaServicesAccount
## SYNOPSIS
Creates a new Azure Media Services account.

## SYNTAX

```
New-AzureMediaServicesAccount [-Name] <String> [-Location] <String> [-StorageAccountName] <String>
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The New-AzureMediaServicesAccount cmdlet creates a new Media Services account with the specified Media Services account name, datacenter location where you want to create the account, and an existing storage account name.
The storage account has to be located in the same data center as the new Media Services account.

## EXAMPLES

### 1: Create a new Media Services account
```
PS C:\> New-AzureMediaServicesAccount -Name "mediaserviceaccount" -StorageAccountName "storageaccount " -Location "West US"
```

## PARAMETERS

### -Location
The Media Services datacenter location.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
The Media Services account name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
The storage account name.
The storage account must already exist in the same datacenter as the new Media Services account.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[How to use Azure PowerShell for Media Services](http://go.microsoft.com/fwlink/?LinkId=324179)

