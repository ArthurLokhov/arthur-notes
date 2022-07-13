# Setting up Visual Studio Code

## Extensions

### Main

- `Better Comments` by Aaron Bond
- `Quit Control for VSCode` by Artur Diniz Adam
- `Path Intellisense` by Christian Kohler
- `EditorConfig for VS Code` by EditorConfig
- `gitignore` by CodeZombie
- `Peek Hidden Files` by Adrian Wilczynski

### C# and .Net
- `C#` by Microsoft
- `Nuget Package Manager` by jmrog
- `Nuget Gallery` by pcislo
- `C# XML Documentation Comments` by Keisuke Kato
- `.NET Core Test Explorer` by Jun Han
- `MSBuild project tools` by tintoy
- `.NET Core Tools` by Jun Han
- `C# Extensions` by JosKreativ

### Customization
- `Night Owl` by sarah.drasner
- `Material Theme Icons` by Equinusocio

## Global settings.json (this file is published in my other repository `arthur-dotfiles`)

1. Hiding extra panels VS Code (I'm a minimalist).

```json
"workbench.activityBar.visible": false,
"workbench.editor.showTabs": false,
"workbench.statusBar.visible": false,
"workbench.editor.showIcons": false,
"workbench.startupEditor": "none",
"breadcrumbs.enabled": false,

"explorer.confirmDelete": false,
"explorer.confirmDragAndDrop": false,

"editor.scrollbar.horizontal": "hidden",
"editor.scrollbar.vertical": "hidden",
"editor.bracketPairColorization.enabled": false,
"editor.guides.indentation": false,
"editor.renderLineHighlight": "none",
"editor.lineNumbers": "interval",
"editor.minimap.enabled": false,
"editor.overviewRulerBorder": false,
```

3. Font Settings
I have only certain ligatures enabled, the rest are disabled.

```json
"editor.fontSize": 14,
"editor.fontLigatures": "'ss01', 'ss02', 'ss03', 'ss04', 'ss05', 'ss06', 'zero', 'onum'",
"editor.fontFamily": "'CaskaydiaCove NF', 'Consolas'",
"editor.fontWeight": "350",
```

Some manipulations with colors, font styles for certain places in the code.

```json
"editor.tokenColorCustomizations": {
    "textMateRules": [
        {
            "scope": [
                "comment",
                "entity.name.type.class",
                "keyword",
                "constant",
                "storage.modifier",
                "storage.type.class.js"
            ],
            "settings": {
                "fontStyle": "italic"
            }
        },
        {
            "scope": [
                "invalid",
                "keyword.operator",
                "constant.numeric.css",
                "keyword.other.unit.px.css",
                "constant.numeric.decimal.js",
                "constant.numeric.json"
            ],
            "settings": {
                "fontStyle": ""
            }
        }
    ]
},
```

4. C# Settings

```json
"omnisharp.enableImportCompletion": true,
"omnisharp.organizeImportsOnFormat": true,
```
