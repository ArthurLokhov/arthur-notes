# Устанока и настройка Manjaro

## Предварительные настройки

1. Установка самых быстрых зеркалов
```sh
sudo pacman-mirrors --fasttrack
```

2. Обновление системы, ядра и программ
```sh
sudo pacman -Syu
```

3. Включение TRIM в том случае, если система стоит на SSD
```sh
sudo systemctl enable fstrim.timer
```

4. (Опционально) Установка ядра Linux на выбор
```sh
mhwd-kernel -li
sudo mhwd-kernel -i [ядро]
```

5. (Опционально) Установка шрифтов от Microsoft
```sh
cd
mkdir ~/tmp
cd ~/tmp
git clone https://aur.archlinux.org/ttf-ms-fonts.git
cd ttf-ms-fonts
makepkg -si
```

## Установка и настройка программ.

### Настройка Firefox Browser
1. Сначала надо узнать папку пользователя для этого заходим в Справка->Информация для решения проблем->Каталог профиля
2. Создать файлик user.js и поместить конфиг из [arthur-dotfiles](https://github.com/ArthurLokhov/arthur-dotfiles)
### Установка Telegram
Просто скачать с официального сайта

## Настройка рабочего окружения
1. Установка VisualStudio Code
```sh
cd
mkdir ~/tmp
cd ~/tmp
git clone https://aur.archlinux.org/visual-studio-code-bin.git
cd visual-studio-code-bin
makepkg -si
```

2. Настройка терминала
```sh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```