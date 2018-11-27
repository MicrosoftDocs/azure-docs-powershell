---
external help file: Microsoft.Azure.Commands.MarketplaceOrdering.dll-Help.xml
Module Name: Az.MarketplaceOrdering
online version:
schema: 2.0.0
---

# Set-AzMarketplaceTerms

## SYNOPSIS
{{Fill in the Synopsis}}

## SYNTAX

### AgreementAcceptParameterSet (Default)
```
Set-AzMarketplaceTerms -Publisher <String> -Product <String> -Name <String> [-Accept]
 [-Terms <PSAgreementTerms>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AgreementRejectParameterSet
```
Set-AzMarketplaceTerms -Publisher <String> -Product <String> -Name <String> [-Reject]
 [-Terms <PSAgreementTerms>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObjectAcceptParametrSet
```
Set-AzMarketplaceTerms [-Accept] [-InputObject] <PSAgreementTerms> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectRejectParametrSet
```
Set-AzMarketplaceTerms [-Reject] [-InputObject] <PSAgreementTerms> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{Fill in the Description}}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Accept
Pass this to accept the legal terms.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AgreementAcceptParameterSet, InputObjectAcceptParametrSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Terms object returned in Get-AzureRmMarketplaceTerms cmdlet.
This is a mandatory parameter if Accept paramter is true.

```yaml
Type: Microsoft.Azure.Commands.MarketplaceOrdering.Models.PSAgreementTerms
Parameter Sets: InputObjectAcceptParametrSet, InputObjectRejectParametrSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Plan identifier string of image being deployed.

```yaml
Type: System.String
Parameter Sets: AgreementAcceptParameterSet, AgreementRejectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Product
Offer identifier string of image being deployed.

```yaml
Type: System.String
Parameter Sets: AgreementAcceptParameterSet, AgreementRejectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publisher
Publisher identifier string of image being deployed.

```yaml
Type: System.String
Parameter Sets: AgreementAcceptParameterSet, AgreementRejectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reject
Pass this to reject the legal terms.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AgreementRejectParameterSet, InputObjectRejectParametrSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Terms
Terms object returned in Get-AzureRmMarketplaceTerms cmdlet.
This is a mandatory parameter if you accept the legal terms.

```yaml
Type: Microsoft.Azure.Commands.MarketplaceOrdering.Models.PSAgreementTerms
Parameter Sets: AgreementAcceptParameterSet, AgreementRejectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.MarketplaceOrdering.Models.PSAgreementTerms

## OUTPUTS

### Microsoft.Azure.Commands.MarketplaceOrdering.Models.PSAgreementTerms

## NOTES

## RELATED LINKS
