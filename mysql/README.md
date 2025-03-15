# mysql cheatsheet

> [!NOTE]
> since im using [arch linux](https://wiki.archlinux.org/title/MySQL), i have
> [mariadb](https://wiki.archlinux.org/title/MariaDB) installed instead

## installation

```bash
sudo pacman -S mariadb

mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql

mariadb-secure-installation

```

more information on [maria db arch wiki](https://wiki.archlinux.org/title/MariaDB)

## creating a database

on terminal

```bash
mysql -u root -p -e "CREATE DATABASE your_database_name;"
```

in my sql after log in

```sql
CREATE DATABASE database_name;

-- show list of databases
SHOW DATABASES;
```

## select a database

```sql
USE database_name;
```

## creating mysql user

```sql
CREATE USER 'the_username'@'localhost' IDENTIFIED BY 'the_password';

-- full privileges
GRANT ALL PRIVILEGES ON database_name.* TO 'the_username'@'localhost';

-- apply changes
FLUSH PRIVILEGES;
```
