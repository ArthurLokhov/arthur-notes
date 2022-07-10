# Установка и настройка PostgreSQL или MariaDB

## Подготовка к установке

1. Обновление зеркал и установка необходимых программ
`mosh` - более безопасный ssh, автоматически восстанавливает соединение, а также работает даже на телефоне
```
sudo apt-get update
sudo apt-get install -y git curl wget zip unzip gcc build-essential make mosh
sudo apt-get install -y libreadline-dev zlibc zlib1g-dev
```

## Установка и настройка PostgreSQL
1. Установка PSQL
```
sudo apt-get update && sudo apt-get install -y postgresql postgresql-contrib
```

2. Создание пользователя и его базы данных

Имя пользователя и базы данных должно совпадать с основным пользователем Linux, тогда можно будет заходить просто использую `psql`.
```
sudo -i -u postgres
createuser --interactive
createdb [user]
exit
```

3. Заходим в базу данных.

Если имя пользователей совпадает.
```
psql
```

Если создан другой пользователь
```
sudo adduser [user]
sudo -u [user] psql
```

Проверем соединение
```
\conninfo
```

Выдаст, что-то похожее:
```
You are connected to database "dfr" as user "dfr" via socket in "/var/run/postgresql" at port "5432".

```

## Установка и настройка MariaDB
1. Установка MariaDB
```
sudo apt-get install -y mariadb-server mariadb-client
sudo mysql_secure_installation
```

2. Создание пользователя и его базы данных

Имя пользователя и базы данных должно совпадать с основным пользователем Linux.
```
sudo mariadb -u root
CREATE DATABASE [user_db] COLLATE 'utf8_general_ci';
CREATE USER [user] IDENTIFIED BY 'some_password';
GRANT ALL privileges ON [user_db] .* TO [user];
```