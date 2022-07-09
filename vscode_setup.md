# Настройка Visual Studio Code
## Плагины
- `Go` by Go Team at Google- основной плагин для работы с Golang.
- `Path Intellisense` by Christian Kohler - автодополнение при манипуляции с путями файлов и директорий.
- `Russian Language Pack for VSCode` by Microsoft - перевод UI приложения на русский.
- `seti-icons` by qinjia - заменяет иконки файлов, также у файлов `.go` иконка с гофером.
- `GlassIt Linux` by nowsci - расширение, чтобы настроить прозрачность VSCode в Linux
## Глобальный settings.json(данный файл опубликован в моем другом репозитории `arthur-dotfiles`)
1. Настройки для Golang
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
``` 
2. Сокрытие лишних панелей VSCode(я минималист)
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

3. Настройки шрифта
У меня включены лишь определенные лигатуры, остальные отключены.
```json
"editor.fontSize": 14,
"editor.fontLigatures": "'ss01', 'ss02', 'ss03', 'ss04', 'ss05', 'ss06', 'zero', 'onum'",
"editor.fontFamily": "'CaskaydiaCove NF', 'Consolas'",
"editor.fontWeight": "350",
```

Некие манипуляции с цветами, стилями шрифта для определенных мест в коде
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
## Дополнительная настройка различных фишек(протестировано только из под Linux)
1. Для установки прозрачности редактора надо установить следующие утилиты
```
sudo apt install -y wmctrl x11-utils bash
```
А также установить расширение `GlassIt Linux` by nowsci