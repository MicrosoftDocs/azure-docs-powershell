---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureServiceProjectRole

## SYNOPSIS
Sets the number of instances or the runtime version of a role.

## SYNTAX

### Instances
```
Set-AzureServiceProjectRole [[-RoleName] <String>] [-Instances] <Int32> [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### Runtime
```
Set-AzureServiceProjectRole [[-RoleName] <String>] [-Runtime] <String> [-Version] <String> [-PassThru]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### VMSize
```
Set-AzureServiceProjectRole [[-RoleName] <String>] [-PassThru] [-VMSize] <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
powershell_prelim

The **Set-AzureServiceProjectRole** cmdlet sets the number of role instances for the specified role.

## EXAMPLES

### 1: Set instances for a web role
```
PS C:\>Set-AzureServiceProjectRole  ¢â‚¬Å"MyWebRole ¢â‚¬Â 2
```

Sets the number of instances for the web role named 'MyWebRole1' to 2.

### 2: Set instances for a worker role
```
PS C:\>Set-AzureServiceProjectRole  ¢â‚¬Å"MyWorkerRole1 ¢â‚¬Â 2
```

Sets the role instance count for the worker role named WorkerRole1 to 2.

### 3: Set the runtime version for a role service
```
PS C:\>Set-AzureServiceProjectRole  ¢â‚¬Å"MyRole1 ¢â‚¬Â node 0.6.20
```

Sets the node.exe runtime version for role  ¢â‚¬Å"MyRole1 ¢â‚¬Â to 0.6.20.

## PARAMETERS

### -RoleName
Specifies the name of the web or worker role to be changed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Instances
Specifies the number of role instances for the specified web or worker role.

```yaml
Type: Int32
Parameter Sets: Instances
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMSize
Specifies the virtual machine size of the role.

```yaml
Type: String
Parameter Sets: VMSize
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Runtime
Specifies the runtime to add to the specified role.

```yaml
Type: String
Parameter Sets: Runtime
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the version of the runtime to add to the role.

```yaml
Type: String
Parameter Sets: Runtime
Aliases: 

Required: True
Position: 3
Default value: None
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
In-memory profile.```yaml
Type: AzureSMProfile
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

###  
Specifies the size of the virtual machine.

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureServiceProject](.\Set-AzureServiceProject.md)

