# Configuring linux

## Configuring the Linux distribution
1. Update the system
```
sudo apt-get update && sudo apt-get upgrade
```
2. Installing `ttf-mscorefonts-installer` using `Software Manager`

3. Setting up the keyboard layout, adding support for the Russian language(I always put the English version of the system, so Russian is not initially available).

4. Installing multi-codecs (look under your distribution) for Linux, in this case Mint
```
sudo apt-get update && sudo apt-get install mint-meta-codecs
```

5. (Optional) Install `Snap`
```
sudo rm /etc/apt/prefernces.d/nosnap.pref
sudo apt-get update && sudo apt-get install snapd
sudo snap version
```

6. (Optional) To configure [TimeShift](https://zen.yandex.ru/media/gothicserge/rezervnoe-kopirovanie-linux-mint-ispolzuem-timeshift-60f01cab584b027c4d32cc64)

7. Restart the computer

## Configuring Drivers
1. Choose from either `nVidia` or `AMD/Intel`

The version of the `nVidia` driver should be found on the `nVidia` website
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

2. Restart the computer

## Configuring software and Linux for everyday use

1. Install 'Yandex Browser` and configure it
Go to [path](browser://flags) and turn on `System windows controls` 
2. Set wallpaper and theme of apps, icons, cursor
3. Install `Telegram`
4. Install `Discord`

## Setting up software for Games

1. Install `Wine`
```
sudo dpkg --add-architecture i386
wget -nc https://dl.winehq.org/wine-builds/winehq.key
sudo apt-key add winehq.key
sudo apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu focal main'
sudo apt-get update
sudo apt-get install --install-recommends wine-staging 

<!-- Often the previous command will install all of this -->
sudo apt-get install libgnutls30:i386 libldap-2.4-2:i386 libgpg-error0:i386 libxml2:i386 libasound2-plugins:i386 libsdl2-2.0-0:i386 libfreetype6:i386 libdbus-1-3:i386 libsqlite3-0:i386
```
2. Install `Lutris`
```
sudo add-apt-repository ppa:lutris-team/lutris
sudo apt-get update
sudo apt-get install lutris
```
3. Installing and configuring `Steam`, connecting `gamemode`
```
sudo apt-get install steam
```
Next, you need to turn on `Steam Play` and restart `Steam` itself.
```
sudo apt-get install gamemode
```

After set in the game launch parameters

`Steam`:
```
gamemoderun %command%
```

`Lutris`:
```
gamemoderun
```

## Basic setup for development
1. Installation of utilities required for assembly and compilation
```
sudo apt-get update
sudo apt-get install -y make git curl wget vim gcc build-essential
```
2. Setting up the terminal

Install [Hack  NF](https://www.nerdfonts.com/font-downloads) or any other
```
mv Hack ~/.local/share/fonts
fc-cache -f -v 
```

```
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```