---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: 
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationRuleObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationRuleObject.md
---

# New-AzSecurityAutomationRuleObject

## SYNOPSIS
Creates security automation rule object

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.security/new-azsecurityautomationruleobject) for up-to-date information.

## SYNTAX

```
New-AzSecurityAutomationRuleObject -PropertyJPath <String> -Operator <String> -ExpectedValue <String>
 -PropertyType <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Creates security automation rule object

## EXAMPLES

### Example 1
```powershell
New-AzSecurityAutomationRuleObject -PropertyJPath 'properties.metadata.severity'  -PropertyType 'String' -Operator 'Equals'  -ExpectedValue 'High'
```

Creates security automation rule object that filters messages that with "High" severity

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpectedValue
The expected value

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operator
A valid comparer operator to use.
A case-insensitive comparison will be applied for String PropertyType

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertyJPath
The JPath of the entity model property that should be checked

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertyType
The data type of the compared operands (string, integer, floating point number or a boolean \[true/false\]\]

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationTriggeringRule

## NOTES

## RELATED LINKS