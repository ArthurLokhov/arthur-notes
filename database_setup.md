# Installing and configuring PostgreSQL or MariaDB

## Preparing for installation

1. Updating mirrors and installing the necessary programs.
`mosh` - more secure ssh, automatically reconnects, and also works even on the phone.
```
sudo apt-get update
sudo apt-get install -y git curl wget zip unzip gcc build-essential make mosh
sudo apt-get install -y libreadline-dev zlibc zlib1g-dev
```

## Installing and configuring PostgreSQL
1. Install PSQL.
```
sudo apt-get update && sudo apt-get install -y postgresql postgresql-contrib
```

2. Creating a user and his database.

The username and database must match the main Linux user, then you can just log in using `psql`.
```
sudo -i -u postgres
createuser --interactive
createdb [user]
exit
```

3. We go into the database.

If the user name matches.
```
psql
```

If another user is created.
```
sudo adduser [user]
sudo -u [user] psql
```

Let's check the connection.
```
\conninfo
```

It will give something like:
```
You are connected to database "dfr" as user "dfr" via socket in "/var/run/postgresql" at port "5432".

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