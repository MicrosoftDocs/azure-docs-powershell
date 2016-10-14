---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
online version: .\Get-AzureStorSimpleAccessControlRecord.md
schema: 2.0.0
---

# Set-AzureStorSimpleAccessControlRecord

## SYNOPSIS
Updates the IQN of an access control record.

## SYNTAX

```
Set-AzureStorSimpleAccessControlRecord [-ACRName] <String> [-IQNInitiatorName] <String> [-WaitForComplete]
 [[-NewName] <String>] [-Profile <AzureProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzureStorSimpleAccessControlRecord** cmdlet updates the iSCSI qualified name (IQN) of an existing access control record.

## EXAMPLES

### Example 1: Update an access control record
```
PS C:\>Set-AzureStorSimpleAccessControlRecord -ACRName "Acr10" -IQNInitiatorName "IqnUpdated" -WaitForComplete
VERBOSE: ClientRequestId: e4766335-f302-40e0-93bf-fad7aa488ae6_PS
VERBOSE: ClientRequestId: cfdbbd67-6ba5-4238-b743-b88f604079b9_PS
VERBOSE: About to run a task to update your Access Control Record! 
VERBOSE: ClientRequestId: d5cf2793-0ab5-40ff-ab6f-43e21bc4c0a4_PS


JobId        : 89502523-52fc-4ce2-b2d4-cb8c6692fb60
JobResult    : Succeeded
JobStatus    : Completed
ErrorCode    : 
ErrorMessage : 
JobSteps     : {}

VERBOSE: The job created for your update operation has completed successfully. 
VERBOSE: ClientRequestId: cbd47519-3a3c-4365-b097-0fb7551c48ee_PS
GlobalId            : 
InitiatorName       : IqnUpdated
InstanceId          : 9bcfbc83-e196-4688-9016-827f51515c24
Name                : Acr10
OperationInProgress : None
VolumeCount         : 0
```

This command updates the access control record named Acr10 for the iSCSI initiator named IqnUpdated.
This command specifies the *WaitForComplete* parameter, and, therefore, the command waits until the operation is complete, and then returns a **TaskStatusInfo** object.

## PARAMETERS

### -ACRName
Specifies a name of the access control record to modify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IQNInitiatorName
Specifies the IQN of the iSCSI initiator to which this cmdlet provides access for the volume.

```yaml
Type: String
Parameter Sets: (All)
Aliases: IQN

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies a new name for access control record.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### -WaitForComplete
Indicates that this cmdlet waits for the operation to complete before it returns control to the Windows PowerShell ‚Â® console.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### TaskStatusInfo, TaskResponse
This cmdlet returns a **TaskStatusInfo** object if you specify the *WaitForComplete* parameter.
If you do not specify that parameter, it returns a **TaskResponse** object.

## NOTES

## RELATED LINKS

[Get-AzureStorSimpleAccessControlRecord](.\Get-AzureStorSimpleAccessControlRecord.md)

[New-AzureStorSimpleAccessControlRecord](.\New-AzureStorSimpleAccessControlRecord.md)

[Remove-AzureStorSimpleAccessControlRecord](.\Remove-AzureStorSimpleAccessControlRecord.md)

