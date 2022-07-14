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
sudo apt-get install -y apt-transport-https ca-certificates software-properties-common gnupg gnupg2 
```

Настройка zsh
```
sudo apt-get install -y zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

## Docker
1. Удаление старых версий Docker'а
```
sudo apt-get remove docker docker-engine docker.io containerd runc
```

2. Установка Docker'а из подключенного репозитория
```
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

3. Установка определенной версии
```
apt-cache madison docker-ce
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io docker-compose-plugin
```

4. Включение/Отключение Docker Engine
```
sudo systemctl start/stop docker.service
sudo systemctl start/stop docker.socket
```