﻿---
external help file: Microsoft.PowerShell.PlatyPS.dll-Help.xml
online version: https://learn.microsoft.com/powershell/module/microsoft.powershell.platyps/import-markdowncommandhelp?view=ps-modules&WT.mc_id=ps-gethelp
Locale: en-US
Module Name: Microsoft.PowerShell.PlatyPS
ms.custom: preview1
ms.date: 10/25/2024
schema: 2.0.0
title: Import-MarkdownCommandHelp
---

# Import-MarkdownCommandHelp

## SYNOPSIS

Imports Markdown help content into **CommandHelp** objects.

## SYNTAX

### Path (Default)

```
Import-MarkdownCommandHelp [-Path] <string[]> [<CommonParameters>]
```

### LiteralPath

```
Import-MarkdownCommandHelp -LiteralPath <string[]> [<CommonParameters>]
```

## DESCRIPTION

The command imports Markdown files containing command help and creates **CommandHelp** objects. The
**CommandHelp** object is a structured representation of the help content that can be used to export
to different formats.

## EXAMPLES

### Example 1 - Import all cmdlet Markdown files in a folder

The following example import cmdlet Markdown files in a folder and converts them to **CommandHelp**
objects. These objects can be used to export to different formats.

```powershell
$mdfiles = Measure-PlatyPSMarkdown -Path .\v2\Microsoft.PowerShell.PlatyPS\*.md
$mdfiles | Where-Object Filetype -match 'CommandHelp' |
    Import-MarkdownCommandHelp -Path {$_.FilePath} |
    Select-Object Title
```

```Output
Title
-----
Compare-CommandHelp
Export-MamlCommandHelp
Export-MarkdownCommandHelp
Export-MarkdownModuleFile
Export-YamlCommandHelp
Export-YamlModuleFile
Import-MamlHelp
Import-MarkdownCommandHelp
Import-MarkdownModuleFile
Import-YamlCommandHelp
Import-YamlModuleFile
Measure-PlatyPSMarkdown
New-CommandHelp
New-MarkdownCommandHelp
New-MarkdownModuleFile
Test-MarkdownCommandHelp
Update-CommandHelp
Update-MarkdownCommandHelp
Update-MarkdownModuleFile
```

## PARAMETERS

### -LiteralPath

Specifies a path to one or more locations containing markdown files. The value of **LiteralPath** is
used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape
characters, enclose it in single quotation marks. Single quotation marks tell PowerShell not to
interpret any characters as escape sequences.

For more information, see
[about_Quoting_Rules](/powershell/module/microsoft.powershell.core/about/about_CommonParameters).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases:
Accepted values:
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Specifies the path to an item. This cmdlet gets the item at the specified location. Wildcard
characters are permitted. This parameter is required, but the parameter name Path is optional.

Use a dot (`.`) to specify the current location. Use the wildcard character (`*`) to specify all
items in the current location.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:
Accepted values:
Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable,
-ProgressAction, -Verbose, -WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.PowerShell.PlatyPS.Model.CommandHelp

## NOTES

## RELATED LINKS

- [Export-MarkdownCommandHelp](Export-MarkdownCommandHelp.md)
- [Export-YamlCommandHelp](Export-YamlCommandHelp.md)
- [Import-YamlCommandHelp](Import-YamlCommandHelp.md)