---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
online version: .\Get-AzureWebsite.md
schema: 2.0.0
---

# Publish-AzureWebsiteProject

## SYNOPSIS
Publish a Visual Studio web project to a Microsoft Azure web site using WebDeploy.

## SYNTAX

### ProjectFile
```
Publish-AzureWebsiteProject [-ProjectFile] <String> [[-Configuration] <String>]
 [[-ConnectionString] <Hashtable>] [-SkipAppData] [-DoNotDelete] [[-Name] <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Package
```
Publish-AzureWebsiteProject [-Package] <String> [[-ConnectionString] <Hashtable>] [-Tokens <String>]
 [-SetParametersFile <String>] [-SkipAppData] [-DoNotDelete] [[-Name] <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Publish a Visual Studio web project to a Microsoft Azure web site using WebDeploy.
It can either take a WebDeploy package and publish directly, or take a Visual Studio web project, build the project and publish.
It can also replace the connection strings in the Web.config during publish.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -Configuration Debug
```

Description

-----------

Build a Visual Studio web project with "Debug" configuration (meaning use Web.Debug.config) and publish to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1.zip
```

Description

-----------

Publish a WebDeploy Pacakge .zip file to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1
```

Description

-----------

Publish a WebDeploy Pacakge folder to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -ConnectionString @{ DefaultConnection = "my connection string" }
```

Description

-----------

Build a Visual Studio web project, overwrite the "DefaultConnection" connection string in Web.config and publish to a Microsoft Azure Web Site using WebDeploy.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -DefaultConnection "my connection string"
```

Description

-----------

Build a Visual Studio web project, overwrite the "DefaultConnection" connection string in Web.config and publish to a Microsoft Azure Web Site using WebDeploy.
Notice that -DefaultConnection is a dynamic parameter which gets added by parsing Web.config.

## PARAMETERS

### -Name
The web site name.

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

### -Slot
The web site slot name.

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

### -ProjectFile
The Visual Studio web application project to be published.

```yaml
Type: String
Parameter Sets: ProjectFile
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Configuration
The configuration used to build the Visual Studio web application project.

```yaml
Type: String
Parameter Sets: ProjectFile
Aliases: 

Required: False
Position: 3
Default value: Release
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Package
The WebDeploy package folder for zip file of the Visual Studio web application project to be published.

```yaml
Type: String
Parameter Sets: Package
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionString
The connection strings to use for the deployment.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DoNotDelete
{{Fill DoNotDelete Description}}

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

### -SetParametersFile
The WebDeploy SetParameters.xml file to transform configuration within the package.```yaml
Type: String
Parameter Sets: Package
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAppData
{{Fill SkipAppData Description}}

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

### -Tokens
The configuration tokens to use for the deployment.```yaml
Type: String
Parameter Sets: Package
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

## NOTES

## RELATED LINKS

[Get-AzureWebsite](.\Get-AzureWebsite.md)

[New-AzureWebsite](.\New-AzureWebsite.md)

[Remove-AzureWebsite](.\Remove-AzureWebsite.md)

[Set-AzureWebsite](.\Set-AzureWebsite.md)

