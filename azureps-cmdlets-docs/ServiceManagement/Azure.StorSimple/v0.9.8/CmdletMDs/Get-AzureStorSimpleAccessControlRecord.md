---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\New-AzureStorSimpleAccessControlRecord.md
schema: 2.0.0
---

# Get-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Gets access control records in a service configuration.

## SYNTAX

```
Get-AzureStorSimpleAccessControlRecord [[-ACRName] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureStorSimpleAccessControlRecord** cmdlet gets access control records in the StorSimple Manager service configuration.
This cmdlet gets all records or a named record.

Access control records are containers of iSCSI initiator parameters.
These parameters specify which initiators can access a volume.
When an iSCSI initiator attempts to connect to a volume, your appliance checks the access control records assigned to that volume.
If the iSCSI initiator parameters match one of the entries in an access control record mapped to that volume, the iSCSI initiator can connect.

## EXAMPLES

### Example 1: Get all access control records
```
PS C:\>Get-AzureStorSimpleAccessControlRecord
InstanceId                           Name                        InitiatorName               VolumeCount
----------                           ----                        -------------               -----------
01a31aa5-14de-4b77-b926-2842577f540e Windows_XYUSFL718-RV_ACR    iqn.1991-05.com.microsof... 3
071c282d-0cd2-4c5f-b687-48966037ba48 Linux_XYUSFL719_ACR         iqn.1994-05.com.redhat:a... 3
4600eade-71f8-4d04-baec-0e7cf1d1e8fb Windows_XYUSFL720_ACR       iqn.1991-05.com.microsof... 9
d508d6f0-fcda-4624-b223-c0b307d6113e Linux_XYUSFL350_ACR         iqn.1991-05.com.microsof... 9
```

This command gets all access control records.

### Example 2: Get a specific access control record
```
PS C:\>Get-AzureStorSimpleAccessControlRecord -ACRName "Acr11"
VERBOSE: ClientRequestId: 61f261c7-acd3-4bcc-922a-ddfd85eb767b_PS
VERBOSE: ClientRequestId: 49c6a4c7-d299-46fd-a553-034c52b47487_PS

GlobalId            : 
InitiatorName       : iqn-contoso63
InstanceId          : 55f24643-ab3a-4098-ade2-aa2b1a3ab18c
Name                : Acr11
OperationInProgress : None
VolumeCount         : 6

VERBOSE: Access Control Record with given name Acr11 is found!
```

This command gets the access control record named Acr11.

## PARAMETERS

### -ACRName
Specifies the name of an access control record to get.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### AccessControlRecord, IList<AccessControlRecord>
This cmdlet returns an **AccessControlRecord** object or an **IList\<AccessControlRecord\>** object.
An **AccessControlRecord** object contains the following fields: 

- **GlobalId** (**String**) 
- **InitiatorName** (**String**) 
- **InstanceId** (**String**) 
- **Name** (**String**) 
- **OperationInProgress** (**OperationInProgress**) 
- **VolumeCount** (**int**)

## NOTES

## RELATED LINKS

[New-AzureStorSimpleAccessControlRecord](.\New-AzureStorSimpleAccessControlRecord.md)

[Remove-AzureStorSimpleAccessControlRecord](.\Remove-AzureStorSimpleAccessControlRecord.md)

[Set-AzureStorSimpleAccessControlRecord](.\Set-AzureStorSimpleAccessControlRecord.md)

