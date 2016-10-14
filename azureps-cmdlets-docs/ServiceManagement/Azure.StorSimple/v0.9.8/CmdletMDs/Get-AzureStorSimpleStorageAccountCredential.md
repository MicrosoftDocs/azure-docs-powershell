---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleStorageAccountCredential.md
schema: 2.0.0
---

# Get-AzureStorSimpleStorageAccountCredential

## SYNOPSIS
Gets credentials for storage accounts.

## SYNTAX

```
Get-AzureStorSimpleStorageAccountCredential [[-StorageAccountName] <String>] [-Profile <AzureProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleStorageAccountCredential** cmdlet gets credentials for storage accounts.
This cmdlet gets all **StorageAccountCredential** objects configured in the service or a named **StorageAccountCredential**.

## EXAMPLES

### Example 1: Get all credentials for a resource
```
PS C:\>Get-AzureStorSimpleStorageAccountCredential
InstanceId                           Login           Name            UseSSL VolumeCount     CloudType    Location
----------                           -----           ----            ------ -----------     ---------    --------
b5e0857f-82ef-4426-883b-a612889ebee4 qwertyuiopa     AdminAccount    True   24              Azure
```

This command gets all available credentials for storage accounts for the current resource.

### Example 2: Get the credential for a specific storage account
```
PS C:\>Get-AzureStorSimpleStorageAccountCredential -StorageAccountName "ContosoCloudStorage"
VERBOSE: ClientRequestId: 16551af6-3398-4d30-a389-1b8eb01ce92c_PS
VERBOSE: ClientRequestId: 5041277d-4044-4b6c-ae19-4ea9e7ae135a_PS
VERBOSE: Storage Access Credential with name ContosoCloudStorage found! 


CloudType                        : Azure
Hostname                         : blob.core.windows.net
InstanceId                       : 8b3cb7bb-963b-4173-9598-52fe230b0350
IsDefault                        : False
Location                         : West US
Login                            : ContosoCloudStorage
Name                             : ContosoCloudStorage
OperationInProgress              : None
Password                         : 
PasswordEncryptionCertThumbprint : 
UseSSL                           : True
VolumeCount                      : 0
```

This command gets the storage account credential for the storage account named ContosoCloudStorage.

## PARAMETERS

### -Profile
Specifies an Azure profile.

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

### -StorageAccountName
Specifies the name of the storage account for which to get credentials.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### StorageAccountCredential, IList<StorageAccountCredential>
This cmdlet returns a **StorageAccountCredential** object, if you specify the *StorageAccountName* parameter, or if you do not specify that parameter, it returns an **IList\<StorageAccountCredential\>** object.

## NOTES

## RELATED LINKS

[New-AzureStorSimpleStorageAccountCredential](.\New-AzureStorSimpleStorageAccountCredential.md)

[Remove-AzureStorSimpleStorageAccountCredential](.\Remove-AzureStorSimpleStorageAccountCredential.md)

[Set-AzureStorSimpleStorageAccountCredential](.\Set-AzureStorSimpleStorageAccountCredential.md)

