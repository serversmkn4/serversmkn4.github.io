---
layout: post
title: "Install Eraport SMK di Ubuntu"
categories: misc
---

## Siapkan Server

## Install Postrgree SQL

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




