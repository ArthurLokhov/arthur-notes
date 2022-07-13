# Настройка Windows и .Net

## Установка эмулятора терминала
Здесь я могу выделить два эмулятора
- Популярный [Windows Terminal](https://docs.microsoft.com/ru-ru/windows/terminal/)
- И мой фаворит [ConEmu](https://conemu.github.io/)

## Установка WinGet
1. Переходим по [ссылке](https://docs.microsoft.com/en-us/windows/package-manager/winget/) и скачиваем WinGet, если он не стоит.
2. Обновляем все программы, которые нашел WinGet
```
winget upgrade --all
```

## Установка Git
```
winget install -e --id Git.Git
```

## Установка Windows PowerToys, QuickLook
1. Установка Window PowerToys
```
winget install Microsoft.PowerToys --source winget
```
2. Переходим по [ссылке](https://apps.microsoft.com/store/detail/quicklook/9NV4BS3L1H4S) и скачиваем QuickLook

## Устанавливаем VisualStudio Code
1. Переходим по [ссылке](https://code.visualstudio.com/) и скачиваем VSCode.
2. Настраиваем settings.json под себя. Мой вариант находится [здесь](https://github.com/ArthurLokhov/arthur-dotfiles)

## Установка CodeTrack
1. Скачать можно [здесь](https://www.getcodetrack.com/releases.html#latest)

## Установка Insomnia
1. Скачать можно [здесь](https://insomnia.rest/download#windows)

## Установка Nuget Package Explorer
1. Скачать можно [здесь](https://apps.microsoft.com/store/detail/nuget-package-explorer/9WZDNCRDMDM3)

## (Опционально) Второстепенный софт
1. Скачать WinDbg можно [здесь](https://apps.microsoft.com/store/detail/windbg-preview/9PGJGD53TN86)
2. Скачать WinMerge можно [здесь](https://winmerge.org/)
3. Скачать Wireshark можно [здесь](https://www.wireshark.org/)
4. Скачать Github Desktop можно [здесь](https://desktop.github.com/)
5. Скачать Богоподобные утилиты NirSoft можно [здесь](http://www.nirsoft.net/)
6. Скачать WinDirStat можно [здесь](https://windirstat.net/)
7. Скачать VLC можно [здесь](https://www.videolan.org/vlc/)

## Установка .Net
1. Скачать можно [здесь](https://dotnet.microsoft.com/en-us/download)

## Включение режима Бога в Windows
1. Создаем папку с названием `God Mode.{ED7BA470-8E54-465E-825C-99712043E01C}`
2. Привязываем папку к панели задач.
3. Profit. 