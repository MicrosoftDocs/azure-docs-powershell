---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-AzureRemoteDesktopFile

## SYNOPSIS
Gets an RDP file for an Azure virtual machine.

## SYNTAX

### Download (Default)
```
Get-AzureRemoteDesktopFile [-Name] <String> [-LocalPath] <String> [-ServiceName] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### Launch
```
Get-AzureRemoteDesktopFile [-Name] <String> [[-LocalPath] <String>] [-Launch] [-ServiceName] <String>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRemoteDesktopFile** cmdlet downloads and saves a remote desktop connection (RDP) file for an Azure virtual machine.
The cmdlet can launch a remote desktop connection to the specified virtual machine.

## EXAMPLES

### Example 1: Get an RDP file
```
PS C:\>Get-AzureRemoteDesktopFile -ServiceName "ContosoService" -Name "VirtualMachine07" -LocalPath "C:\temp\VirtualMachine07.rdp"
```

This command gets an RDP file for the VirtualMachine07 virtual machine named VirtualMachine07 that runs on the service named ContosoService.
The command stores that file as C:\temp\VirtualMachine07.rdp.

### Example 2: Start a remote session
```
PS C:\>Get-AzureRemoteDesktopFile -ServiceName "ContosoService" -Name "VirtualMachine07" -Launch
```

This command gets an RDP file for the VirtualMachine07 virtual machine named VirtualMachine07 that runs on the service named ContosoService.
The command launches a remote desktop session.
The command deletes the RDP file when the connection is closed.

## PARAMETERS

### -Name
Specifies the virtual machine for which this cmdlet downloads an RDP file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: InstanceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalPath
Specifies the full path of the downloaded RDP file on the local computer.

```yaml
Type: String
Parameter Sets: Download
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Launch
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Specifies the name of the Azure service to which the virtual machine belongs.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the Azure profile from which this cmdlet reads.
If you do not specify a profile, this cmdlet reads from the local default profile.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
@{Text=}```yaml
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
@{Text=}```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Launch
Indicates that this cmdlet starts a remote desktop session to the virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: Launch
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

