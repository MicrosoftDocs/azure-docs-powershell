---
external help file: SMAzure_Compute.xml
online version: 4b060a7d-da50-45ff-adb6-bcba63faa90b
schema: 2.0.0
---

# Get-WAPackVMSizeProfile
## SYNOPSIS
Gets size profile objects.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WAPackVMSizeProfile [[-ID] <Guid>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WAPackVMSizeProfile [[-Name] <String>]
```

## DESCRIPTION
These topics are deprecated and will be removed in the future.
For the updated topics, see  Azure WAPack Cmdletshttp://msdn.microsoft.com/library/dn776450.aspx.
This topic describes the cmdlet in the 0.8.1 version of the Microsoft Azure PowerShell module.
To find out the version of the module you're using, from the Azure PowerShell console, type (get-module azure).version.

The Get-WAPackVMSizeProfile cmdlet gets size profile objects for virtual machines.

## EXAMPLES

### Example 1: Get a size profile by using a name
```
PS C:\>Get-WAPackVMSizeProfile -Name "ContosoSizeProfile07"
```

This command gets the size profile named ContosoSizeProfile07.

### Example 2: Get a size profile by using an ID
```
PS C:\>Get-WAPackVMSizeProfile -ID 66242D17-189F-480D-87CF-8E1D749998C8
```

This command gets the size profile that has the specified ID.

### Example 3: Get all size profiles
```
PS C:\>Get-WAPackVMSizeProfile
```

This command gets all the size profiles.

## PARAMETERS

### -ID
Specifies the unique ID of a size profile.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a size profile.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WAPackVM](4b060a7d-da50-45ff-adb6-bcba63faa90b)

