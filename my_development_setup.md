# Setting up my work environment(Linux)

## Предварительная настройка

Изменения публичных зеркал. Я использую (mirror.yandex.ru)
```
cp /etc/apt/sources.list ~/
nano /etc/apt/source.list
```

Скачивание необходимых утилит
```
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install -y git curl wget mosh
sudo apt-get install -y gcc make build-essential
sudo apt-get install -y neofetch lsb-release
sudo apt-get install -y apt-transport-https ca-certificates software-properties-common gnupg2 
```

Настройка zsh
```
sudo apt-get install -y zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

## Установка Docker

Подключаем репозиторий с Docker
```
sudo apt-get update
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
sudo apt-get update
```

Убедитесь, что установка пойдет из репозитория Docker, а не Debian.
```
apt-cache policy docker-ce
```

Устанавливаем Docker
```
sudo apt install docker-ce
sudo systemctl status docker
```