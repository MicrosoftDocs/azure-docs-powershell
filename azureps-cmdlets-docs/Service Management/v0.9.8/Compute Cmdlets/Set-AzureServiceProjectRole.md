---
external help file: SMAzure_Compute.xml
online version: 
schema: 2.0.0
---

# Set-AzureServiceProjectRole
## SYNOPSIS
Sets the number of instances or the runtime version of a role.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-AzureServiceProjectRole [[-RoleName] <String>] [-Instances] <Int32> [-PassThru]
```

### UNNAMED_PARAMETER_SET_2
```
Set-AzureServiceProjectRole [[-RoleName] <String>] [-Runtime] <String> [-Version] <String> [-PassThru]
```

### UNNAMED_PARAMETER_SET_3
```
Set-AzureServiceProjectRole [[-RoleName] <String>] [-PassThru] -VMSize <String>
```

## DESCRIPTION
This topic describes the cmdlet in the 0.8.10 version of the Microsoft Azure PowerShell module.
To get the version of the module you're using, in the Azure PowerShell console, type (Get-Module -Name Azure).Version.

The Set-AzureServiceProjectRole cmdlet sets the number of role instances for the specified role.

## EXAMPLES

### 1: Set instances for a web role
```
PS C:\>Set-AzureServiceProjectRole â€œMyWebRoleâ€ 2
```

Sets the number of instances for the web role named 'MyWebRole1' to 2.

### 2: Set instances for a worker role
```
PS C:\>Set-AzureServiceProjectRole â€œMyWorkerRole1â€ 2
```

Sets the role instance count for the worker role named WorkerRole1 to 2.

### 3: Set the runtime version for a role service
```
PS C:\>Set-AzureServiceProjectRole â€œMyRole1â€ node 0.6.20
```

Sets the node.exe runtime version for role â€œMyRole1â€ to 0.6.20.

## PARAMETERS

### -Instances
Specifies the number of role instances for the specified web or worker role.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
@{Text=}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleName
Specifies the name of the web or worker role to be changed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Runtime
Specifies the runtime to add to the specified role.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the version of the runtime to add to the role.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 3
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMSize
Specifies the virtual machine size of the role.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: 
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### 
Specifies the size of the virtual machine.

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureServiceProject](c3baa783-e57a-46bd-abe4-6d06130eaaf0)

