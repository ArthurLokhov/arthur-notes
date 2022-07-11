# Setting up my work environment
## Pre-setup

1. Updating the system and installing dependencies.
```
sudo apt update && sudo apt upgrade && sudo apt dist-upgrade
sudo apt install build-essential gcc make
sudo apt install software-properties-common ca-certificates apt-transport-https
``` 

2. Find out if php is in our system and write the result in packages.txt
```
dpkg -l | grep php | tee packages.txt
cat packages.txt
rm -rf packages.txt
```

3. We delete the old version of php, if we found it.
```
sudo apt-get purge '^php*.*.*'
```

4. Find out the php version in the official repository.
```
sudo apt show php
```

## Installing and configuring PHP
1. Installing PHP from PPA:ondrej/php
```
sudo apt-get install -y language-pack-en-base
sudo LC_ALL=en_US.UTF-8 add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install php8.1
sudo apt install -y php8.1-cli php8.1-common php8.1-mysql php8.1-zip php8.1-gd php8.1-mbstring php8.1-curl php8.1-xml php8.1-bcmath

```
## Installing and configuring Composer
```
curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php
HASH=`curl -sS https://composer.github.io/installer.sig`
echo $HASH
php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer
composer --version
```
## Installing and configuring MariaDB
1. Install MariaDB.
```
sudo apt-get install -y mariadb-server mariadb-client
sudo mysql_secure_installation
```

2. Creating a user and his database.

The user and database name must match the primary Linux user.
```
sudo mariadb -u root
CREATE DATABASE [user_db] COLLATE 'utf8_general_ci';
CREATE USER [user] IDENTIFIED BY 'some_password';
GRANT ALL privileges ON [user_db] .* TO [user];
```

## Installing and configuring Apache
```
sudo apt install apache2
service apache2 status
service apache2 restart/start/stop
```