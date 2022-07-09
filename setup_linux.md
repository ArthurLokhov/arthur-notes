# Настройка linux

## Настройка Linux дистрибутива
1. Обновить систему
```
sudo apt-get update && sudo apt-get upgrade
```
2. Установка `ttf-mscorefonts-installer` с помощью `Software Manager`

3. Настройка раскладки клавиатуры, добавление поддержки русского языка (Я всегда ставлю английскую версию системы, поэтому русского изначально нима)

4. Установка мульти-кодеков (смотреть под свой дистрибутив) для Linux, в данном случае Mint
```
sudo apt-get update && sudo apt-get install mint-meta-codecs
```

5. (Опционально) Установить `Snap`
```
sudo rm /etc/apt/prefernces.d/nosnap.pref
sudo apt-get update && sudo apt-get install snapd
sudo snap version
```

6. (Опционально) Настроить [TimeShift](https://zen.yandex.ru/media/gothicserge/rezervnoe-kopirovanie-linux-mint-ispolzuem-timeshift-60f01cab584b027c4d32cc64)

7. Перезагрузить компьютер

## Настройка драйверов
1. На выбор либо `nVidia`, либо `AMD/Intel`

Версию драйвера `nVidia` надо узнать на сайте `nVidia`
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get install nvidia-driver-[version] libnvidia-gl-[version] libnvidia-gl-[version]:i386
sudo apt-get install libvulkan1 libvulkan1:i386 
```

```
sudo dpkg --add-architecture i386
sudo apt-get install libgl1-mesa-dri:i386
sudo apt-get install mesa-vulkan-drivers mesa-vulkan-drivers:i386
```

2. Перезагрузить компьютер

## Настройка программного обеспечения и Linux для повседневного использования

1. Установить `Yandex Browser` и настроить его
Переходим по [пути](browser://flags) и включаем `System window controls` 
2. Установить обои и тему приложений, иконок, курсора
3. Установить `Telegram`
4. (Опционально) Установить `Discord`

## Настройка программного обеспечения для игр

1. Установка `Wine`
```
sudo dpkg --add-architecture i386
wget -nc https://dl.winehq.org/wine-builds/winehq.key
sudo apt-key add winehq.key
sudo apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu focal main'
sudo apt-get update
sudo apt-get install --install-recommends wine-staging 

<!-- Зачастую предыдущая команда установит все это -->
sudo apt-get install libgnutls30:i386 libldap-2.4-2:i386 libgpg-error0:i386 libxml2:i386 libasound2-plugins:i386 libsdl2-2.0-0:i386 libfreetype6:i386 libdbus-1-3:i386 libsqlite3-0:i386
```
2. Установка `Lutris`
```
sudo add-apt-repository ppa:lutris-team/lutris
sudo apt-get update
sudo apt-get install lutris
```
3. Установка и настройка `Steam`, подключение `gamemode`
```
sudo apt-get install steam
```
Дальше требуется включить `Steam Play` и перезапустить сам `Steam`.
```
sudo apt-get install gamemode
```

После установить в параметрах запуска игры 

`Steam`:
```
gamemoderun %command%
```

`Lutris`:
```
gamemoderun
```

## Настройка программного обеспечения для разработки(Golang)
1. Установка необходимых для сборки и компиляции утилит
```
sudo apt-get update
sudo apt-get install -y make git curl wget vim gcc build-essential
```
2. Настройка терминала

Установить [Hack  NF](https://www.nerdfonts.com/font-downloads) или любой другой
```
mv Hack ~/.local/share/fonts
fc-cache -f -v 
```

```
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

3. Установка Golang
Позже появится

4. Установка PSQL/MongoDB
Позже появится=