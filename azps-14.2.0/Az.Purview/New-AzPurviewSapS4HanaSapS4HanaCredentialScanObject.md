---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://learn.microsoft.com/powershell/module/Az.Purview/new-azpurviewsaps4hanasaps4hanacredentialscanobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject.md
---

# New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject

## SYNOPSIS
Create an in-memory object for SapS4HanaSapS4HanaCredentialScan.

## SYNTAX

```
New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject [-ClientId <String>] [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-ConnectedViaReferenceName <String>] [-CredentialReferenceName <String>]
 [-CredentialType <String>] [-JCoLibraryPath <String>] [-MaximumMemoryAllowedInGb <String>]
 [-MitiCache <String>] [-ScanRulesetName <String>] [-ScanRulesetType <String>] [-Worker <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for SapS4HanaSapS4HanaCredentialScan.

## EXAMPLES

### Example 1: Create SAPS4 Hana Credential Scan Object
```powershell
New-AzPurviewSapS4HanaSapS4HanaCredentialScanObject -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -ClientId '444' -CredentialReferenceName 'fdsafsdf' -CredentialType 'BasicAuth' -MaximumMemoryAllowedInGb 4 -JCoLibraryPath 'file://asdas' -ConnectedViaReferenceName 'IntegrationRuntime-NJh'
```

```output
ClientId                  : 444
CollectionLastModifiedAt  :
CollectionReferenceName   : parv-brs-2
CollectionType            : CollectionReference
ConnectedViaReferenceName : IntegrationRuntime-NJh
CreatedAt                 :
CredentialReferenceName   : fdsafsdf
CredentialType            : BasicAuth
Id                        :
JCoLibraryPath            : file://asdas
Kind                      : SapS4HanaSapS4HanaCredential
LastModifiedAt            :
MaximumMemoryAllowedInGb  : 4
MitiCache                 :
Name                      :
Result                    :
ScanRulesetName           :
ScanRulesetType           :
Worker                    :
```

Create SAPS4 Hana Credential Scan Object

## PARAMETERS

### -ClientId

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionReferenceName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionType

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectedViaReferenceName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CredentialReferenceName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CredentialType

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JCoLibraryPath

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumMemoryAllowedInGb

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MitiCache

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanRulesetName

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScanRulesetType

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Worker

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.SapS4HanaSapS4HanaCredentialScan

## NOTES

## RELATED LINKS
