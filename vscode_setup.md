# Setting up Visual Studio Code
## Extensions

### Main
- `Better Comments` by Aaron Bond
- `Path Intellisense` by Christian Kohler
- `EditorConfig for VS Code` by EditorConfig
- `Semicolon Insertation Shortcut` by Christian Valentian

### Customization
- `Material Icon Theme` by Philipp Kief
- `Night Owl` by sarah.drasner

## Global settings.json (this file is published in my other repository `arthur-dotfiles`)
<!-- 1. Настройки для Golang
Если файл покрыт тестами, то в редакторе будет подсвечиваться какие функции покрыты, а какие еще нет.
```json
"go.coverOnSave": true,
"go.coverageDecorator": {
    "type": "gutter",
    "coveredHighlightColor": "rgba(64,128,128,0.5)",
    "uncoveredHighlightColor": "rgba(128,64,64,0.25)",
    "coveredGutterStyle": "blockgreen",
    "uncoveredGutterStyle": "blockred",
},
"go.coverOnSingleTest": true,
``` -->
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