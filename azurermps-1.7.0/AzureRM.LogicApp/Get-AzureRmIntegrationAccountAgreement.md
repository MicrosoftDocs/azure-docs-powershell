---
external help file: Microsoft.Azure.Commands.LogicApp.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRmIntegrationAccountAgreement

## SYNOPSIS
Gets the specified integration account agreement from the Azure resource group.

## SYNTAX

```
Get-AzureRmIntegrationAccountAgreement [-ResourceGroupName <String>] [-Name <String>] [-AgreementName <String>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
This is the Description section

The Get-AzureRmIntegrationAccountAgreement cmdlet retrieves integration account agreement from the Azure resource group and returns an object that represents the integration account agreement.
Use this cmdlet to get the integration account agreement from specified resource group.
You can get the integration account agreement by specifying the integration account name, resource group name and agreement name.
To use the dynamic parameters, just type them in the command, or type a hyphen sign (-) to indicate a parameter name and then press the TAB key repeatedly to cycle through the available parameters.
If you miss a required template parameter, the cmdlet prompts you for the value.

## EXAMPLES

### --------------------------  Example 1 : Get the integration account agreement by name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountAgreement -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1" -AgreementName "IntegrationAccountAgreement1"
```

This command gets the integration account agreement by name.

Id                     : /subscriptions/\<SubscriptionId\>/resourceGroups/\<ResourceGroup1\>/providers/Microsoft.Logic/integrationAccounts/TestIntegrationAccount/agreements/IntegrationAccount1
Name                   : IntegrationAccount1
Type                   : Microsoft.Logic/integrationAccounts/agreements
CreatedTime            : 3/24/2016 9:08:46 PM
ChangedTime            : 3/24/2016 9:08:59 PM
AgreementType          : AS2
HostPartner            : TestHost
GuestPartner           : TestGuest
HostIdentityQualifier  : XX
HostIdentityValue      : BB
GuestIdentityQualifier : ZZ
GuestIdentityValue     : AA
Content                : {"AS2":{"ReceiveAgreement":{"SenderBusinessIdentity":{"Qualifier":"AA","Value":"AA"},"ReceiverBusinessIdentity":{"Qualifier":"ZZ
                         ","Value":"ZZ"},"ProtocolSettings":{"MessageConnectionSettings":{"IgnoreCertificateNameMismatch":true,"SupportHttpStatusCodeCont
                         inue":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"AcknowledgementConnectionSettings":{"IgnoreCertificateNameM
                         ismatch":true,"SupportHttpStatusCodeContinue":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"MdnSettings":{"Need
                         Mdn":true,"SignMdn":true,"SendMdnAsynchronously":true,"ReceiptDeliveryUrl":"http://tempuri.org","DispositionNotificationTo":"htt
                         p://tempuri.org","SignOutboundMdnIfOptional":true,"MdnText":"Sample","SendInboundMdnToMessageBox":true,"MicHashingAlgorithm":1},
                         "SecuritySettings":{"OverrideGroupSigningCertificate":true,"SigningCertificate":{"PrivateCertificate":"Cert3","PublicCertificate
                         ":"Cert4"},"EncryptionCertificate":{"PrivateCertificate":"Cert1","PublicCertificate":"Cert2"},"EnableNrrForInboundEncodedMessage
                         s":true,"EnableNrrForInboundDecodedMessages":true,"EnableNrrForOutboundMdn":true,"EnableNrrForOutboundEncodedMessages":true,"Ena
                         bleNrrForOutboundDecodedMessages":true,"EnableNrrForInboundMdn":true},"ValidationSettings":{"OverrideMessageProperties":true,"En
                         cryptMessage":true,"SignMessage":true,"CompressMessage":true,"CheckDuplicateMessage":true,"InterchangeDuplicatesValidityDays":10
                         0,"CheckCertificateRevocationListOnSend":true,"CheckCertificateRevocationListOnReceive":true,"EncryptionAlgorithm":4},"EnvelopeS
                         ettings":{"MessageContentType":"text/plain","TransmitFileNameInMimeHeader":true,"FileNameTemplate":"Test","SuspendMessageOnFileN
                         ameGenerationError":true,"AutogenerateFileName":true},"ErrorSettings":{"SuspendDuplicateMessage":true,"ResendIfMdnNotReceived":t
                         rue}}},"SendAgreement":{"SenderBusinessIdentity":{"Qualifier":"ZZ","Value":"ZZ"},"ReceiverBusinessIdentity":{"Qualifier":"AA","V
                         alue":"AA"},"ProtocolSettings":{"MessageConnectionSettings":{"IgnoreCertificateNameMismatch":true,"SupportHttpStatusCodeContinue
                         ":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"AcknowledgementConnectionSettings":{"IgnoreCertificateNameMisma
                         tch":true,"SupportHttpStatusCodeContinue":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"MdnSettings":{"NeedMdn"
                         :true,"SignMdn":true,"SendMdnAsynchronously":true,"ReceiptDeliveryUrl":"http://tempuri.org","DispositionNotificationTo":"http://
                         tempuri.org","SignOutboundMdnIfOptional":true,"MdnText":"Sample","SendInboundMdnToMessageBox":true,"MicHashingAlgorithm":1},"Sec
                         uritySettings":{"OverrideGroupSigningCertificate":true,"SigningCertificate":{"PrivateCertificate":"Cert3","PublicCertificate":"C
                         ert4"},"EncryptionCertificate":{"PrivateCertificate":"Cert1","PublicCertificate":"Cert2"},"EnableNrrForInboundEncodedMessages":t
                         rue,"EnableNrrForInboundDecodedMessages":true,"EnableNrrForOutboundMdn":true,"EnableNrrForOutboundEncodedMessages":true,"EnableN
                         rrForOutboundDecodedMessages":true,"EnableNrrForInboundMdn":true},"ValidationSettings":{"OverrideMessageProperties":true,"Encryp
                         tMessage":true,"SignMessage":true,"CompressMessage":true,"CheckDuplicateMessage":true,"InterchangeDuplicatesValidityDays":100,"C
                         heckCertificateRevocationListOnSend":true,"CheckCertificateRevocationListOnReceive":true,"EncryptionAlgorithm":4},"EnvelopeSetti
                         ngs":{"MessageContentType":"text/plain","TransmitFileNameInMimeHeader":true,"FileNameTemplate":"Test","SuspendMessageOnFileNameG
                         enerationError":true,"AutogenerateFileName":true},"ErrorSettings":{"SuspendDuplicateMessage":true,"ResendIfMdnNotReceived":true}
                         }}},"X12":null,"Edifact":null}
Metadata               :

### --------------------------  Example 2 : Get the integration account agreements by resource group name.  --------------------------
@{paragraph=PS C:\\\>}



```
Get-AzureRmIntegrationAccountAgreement -ResourceGroupName "ResourceGroup1" -Name "IntegrationAccount1"
```

This command gets the integration account agreements by resource group name.

Id                     : /subscriptions/\<SubscriptionId\>/resourceGroups/\<ResourceGroup1\>/providers/Microsoft.Logic/integrationAccounts/TestIntegrationAccount/agreements/IntegrationAccount1
Name                   : IntegrationAccount1
Type                   : Microsoft.Logic/integrationAccounts/agreements
CreatedTime            : 3/24/2016 9:08:46 PM
ChangedTime            : 3/24/2016 9:08:59 PM
AgreementType          : AS2
HostPartner            : TestHost
GuestPartner           : TestGuest
HostIdentityQualifier  : XX
HostIdentityValue      : BB
GuestIdentityQualifier : ZZ
GuestIdentityValue     : AA
Content                : {"AS2":{"ReceiveAgreement":{"SenderBusinessIdentity":{"Qualifier":"AA","Value":"AA"},"ReceiverBusinessIdentity":{"Qualifier":"ZZ
                         ","Value":"ZZ"},"ProtocolSettings":{"MessageConnectionSettings":{"IgnoreCertificateNameMismatch":true,"SupportHttpStatusCodeCont
                         inue":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"AcknowledgementConnectionSettings":{"IgnoreCertificateNameM
                         ismatch":true,"SupportHttpStatusCodeContinue":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"MdnSettings":{"Need
                         Mdn":true,"SignMdn":true,"SendMdnAsynchronously":true,"ReceiptDeliveryUrl":"http://tempuri.org","DispositionNotificationTo":"htt
                         p://tempuri.org","SignOutboundMdnIfOptional":true,"MdnText":"Sample","SendInboundMdnToMessageBox":true,"MicHashingAlgorithm":1},
                         "SecuritySettings":{"OverrideGroupSigningCertificate":true,"SigningCertificate":{"PrivateCertificate":"Cert3","PublicCertificate
                         ":"Cert4"},"EncryptionCertificate":{"PrivateCertificate":"Cert1","PublicCertificate":"Cert2"},"EnableNrrForInboundEncodedMessage
                         s":true,"EnableNrrForInboundDecodedMessages":true,"EnableNrrForOutboundMdn":true,"EnableNrrForOutboundEncodedMessages":true,"Ena
                         bleNrrForOutboundDecodedMessages":true,"EnableNrrForInboundMdn":true},"ValidationSettings":{"OverrideMessageProperties":true,"En
                         cryptMessage":true,"SignMessage":true,"CompressMessage":true,"CheckDuplicateMessage":true,"InterchangeDuplicatesValidityDays":10
                         0,"CheckCertificateRevocationListOnSend":true,"CheckCertificateRevocationListOnReceive":true,"EncryptionAlgorithm":4},"EnvelopeS
                         ettings":{"MessageContentType":"text/plain","TransmitFileNameInMimeHeader":true,"FileNameTemplate":"Test","SuspendMessageOnFileN
                         ameGenerationError":true,"AutogenerateFileName":true},"ErrorSettings":{"SuspendDuplicateMessage":true,"ResendIfMdnNotReceived":t
                         rue}}},"SendAgreement":{"SenderBusinessIdentity":{"Qualifier":"ZZ","Value":"ZZ"},"ReceiverBusinessIdentity":{"Qualifier":"AA","V
                         alue":"AA"},"ProtocolSettings":{"MessageConnectionSettings":{"IgnoreCertificateNameMismatch":true,"SupportHttpStatusCodeContinue
                         ":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"AcknowledgementConnectionSettings":{"IgnoreCertificateNameMisma
                         tch":true,"SupportHttpStatusCodeContinue":true,"KeepHttpConnectionAlive":true,"UnfoldHttpHeaders":true},"MdnSettings":{"NeedMdn"
                         :true,"SignMdn":true,"SendMdnAsynchronously":true,"ReceiptDeliveryUrl":"http://tempuri.org","DispositionNotificationTo":"http://
                         tempuri.org","SignOutboundMdnIfOptional":true,"MdnText":"Sample","SendInboundMdnToMessageBox":true,"MicHashingAlgorithm":1},"Sec
                         uritySettings":{"OverrideGroupSigningCertificate":true,"SigningCertificate":{"PrivateCertificate":"Cert3","PublicCertificate":"C
                         ert4"},"EncryptionCertificate":{"PrivateCertificate":"Cert1","PublicCertificate":"Cert2"},"EnableNrrForInboundEncodedMessages":t
                         rue,"EnableNrrForInboundDecodedMessages":true,"EnableNrrForOutboundMdn":true,"EnableNrrForOutboundEncodedMessages":true,"EnableN
                         rrForOutboundDecodedMessages":true,"EnableNrrForInboundMdn":true},"ValidationSettings":{"OverrideMessageProperties":true,"Encryp
                         tMessage":true,"SignMessage":true,"CompressMessage":true,"CheckDuplicateMessage":true,"InterchangeDuplicatesValidityDays":100,"C
                         heckCertificateRevocationListOnSend":true,"CheckCertificateRevocationListOnReceive":true,"EncryptionAlgorithm":4},"EnvelopeSetti
                         ngs":{"MessageContentType":"text/plain","TransmitFileNameInMimeHeader":true,"FileNameTemplate":"Test","SuspendMessageOnFileNameG
                         enerationError":true,"AutogenerateFileName":true},"ErrorSettings":{"SuspendDuplicateMessage":true,"ResendIfMdnNotReceived":true}
                         }}},"X12":null,"Edifact":null}
Metadata               :

## PARAMETERS

### -AgreementName
Specifies a name for the integration account agreement.
This parameter is optional.

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

### -InformationAction
@{Text=}

```yaml
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
@{Text=}

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the integration account.
This parameter is optional.

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

### -ResourceGroupName
Specifies a name for the resource group.
This parameter is required.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Management.Logic.Models.IntegrationAccountAgreement

## NOTES

## RELATED LINKS

[New-AzureRmIntegrationAccountAgreement]()

[Set-AzureRmIntegrationAccountAgreement]()

[Remove-AzureRmIntegrationAccountAgreement]()

