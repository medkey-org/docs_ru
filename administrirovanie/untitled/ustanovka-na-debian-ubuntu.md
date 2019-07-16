---
description: Как установить свободную МИС Медкей на Debian-подобные ОС
---

# Установка на Debian/Ubuntu

## Установка на Debian 9 Stretch

Установка производится на операционную систему без графического интерфейса, либо на операционную систему с графическим терминалом.

### Исходные условия

* Установлена ОС Debian 9 Stretch;
* Имеется root-доступ \(sudo-доступ\);
* Установлен веб-сервер Apache2;
* Установлена СУБД PostgreSQL;
* Установлен PHP 7.2;
* Создана чистая база данных и пользователь базы данных, база данных доступна с сервера приложений.

### Шаги по установке

1. Выберите необходимую сборку МИС Медкей в [репозитории сборок](https://medkey.org/ru/repository) \(или на странице «[Загрузить МИС Медкей](https://medkey.org/ru/downloads/)»\);
2. Создайте файл виртуального хоста в каталоге `/etc/apache2/sites-available`:
   1. `touch /etc/apache2/sites-available/medkey`
3. Скопируйте в файл текст, указанный ниже в блоке «Конфигурационный файл виртуального хоста для Apache2».
4. Выполните активацию виртуального хоста и перезапустите веб-сервер Apache2:
   1. `a2ensite medkey`
   2. `service apache2 reload`
5. Скачайте установочный пакет МИС Медкей:
   1. `cd /tmp` // Перейти во временный каталог;
   2. `wget --output-document medkey.tar.gz https://bitbucket.org/medkey/builds/downloads/medkey_версия.tar.gz` // Следует заменить ссылку на скопированную из [репозитория](https://medkey.org/ru/repository) с актуальной версией.
6. Распакуйте архив в каталоге веб-сервера /var/www при помощи команды tar -zxvf:
   1. `cp medkey.tar.gz -t /var/www` // Скопировать файл в месторасположение
   2. `cd /var/www` // Перейти в каталог
   3. `tar -zxvf medkey.tar.gz` // Выполнить распаковку архива
7. Скопируйте файл env.prod.php в env.php: `cp env.prod.php env.php`
8. Внутри файла \`env.php\` при помощи текстового редактора установите параметры подключения к базе данных \(рекомендуется PostgreSQL\):
   1. `define('APP_DB_HOST', '127.0.0.1');` // IP-адрес сервера базы данных
   2. `define('APP_DB_PORT', '5432');` // Порт кластера базы данных
   3. `define('APP_DB_NAME', 'medkey');` // Имя базы данных
   4. `define('APP_DB_USERNAME', 'postgres');` // Пользователь базы данных
   5. `define('APP_DB_PASSWORD', '12345');` // Пароль базы данных
9. Выполните команду формирования структуры базы данных:
   1. `php medkey migrate`
10. Выполните команду установки наборов данных по умолчанию:
    1. `php medkey seed package install`

### Проверка установки

Выполните тестовый вход в веб-интерфейс системы под учётной записью \`admin:admin\` \(логин:пароль\) при помощи браузера.

## Установка на Ubuntu Server 18.04 Bionic Beaver

Установка производится на операционную систему без графического интерфейса.

#### Исходные условия

#### Шаги по установке

#### Проверка установки

### Примеры конфигурации

#### Конфигурационный файл виртуального хоста для веб-сервера Apache2

```text
<VirtualHost *:80>
    ServerName medkey.local

    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/medkey/web

    <Directory /var/www/medkey/web>
        RewriteEngine on
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteRule . index.php

        Options Indexes FollowSymLinks MultiViews
        AllowOverride None
        Order allow,deny
        allow from all
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/medkey.error.log
    CustomLog ${APACHE_LOG_DIR}/medkey.access.log combined
</VirtualHost>
```

