---
layout: post
---

## Siapkan Server

[Install Ubuntu](https://serversmkn4.github.io/2024/07/07/install-server-ubuntu-keamanan-dasar.html)

## Install Postrgree SQL
`sudo apt update`

`sudo apt install postgresql postgresql-contrib`

`sudo systemctl start postgresql`

`sudo systemctl enable postgresql`

`sudo -i -u postgres`

`psql`

```
CREATE DATABASE mydatabase;
CREATE USER myuser WITH ENCRYPTED PASSWORD 'mypassword';
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;
```

`\q`

`exit`

### Memulihkan database

`pg_restore -U username -d database_name -v /path/to/destination/backup_file.sql`


## Download Aplikasi Eraaport 

### Lengkapi kebutuhan server
- PHP >= 8.1.0
- Ctype PHP Extension
- cURL PHP Extension
- DOM PHP Extension
- Fileinfo PHP Extension
- Filter PHP Extension
- Hash PHP Extension
- Mbstring PHP Extension
- OpenSSL PHP Extension
- PCRE PHP Extension
- PDO PHP Extension
- Session PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension

`git clone https://github.com/eraporsmk/erapor7.git dataweb`

`cd dataweb`

`cp .env.example .env`

`nano .env`

```
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=db_name
DB_USERNAME=db_user
DB_PASSWORD=db_pass
```

`composer install`

`php artisan key:generate`

`php artisan migrate`

`php artisan db:seed`




