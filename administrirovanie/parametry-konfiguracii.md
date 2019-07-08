# Параметры конфигурации

Базовые параметры работы МИС Медкей описываются в файле `.env`, который расположен в корневом каталоге приложения.

В дистрибутиве имеются примеры конфигурационного файла `.env`:

* `.env.prod` — пример конфигурационного файла окружения для продакшн-использования;
* `.env.dev` — пример конфигурационного файла окружения для разработки \(отладки\).

Каждый параметр в `.env` файле должен быть описан в отдельной строке.

## Описание параметров .env

### APP\_ENV

Определяет окружение приложения. Может иметь 2 значения:

* `prod` — продакшн-окружение;
* `dev` — окружение для разработки.

В значении продакшн-окружения отключен вывод ошибок приложения на экран \(пользователь не увидит стек ошибки, а получит от сервера страницу с HTTP 500 или другим кодом ошибки, соответствующим произошедшему инциденту\). При этом ошибки будут фиксироваться в журнале приложения.

### APP\_DEBUG

Может принимать значение `true` или `false`. Если значение `true` — в нижней правой части страницы будет отображаться отладочная панель.

Для продакшн-использования должно иметь значение `false`.

### APP\_DB\_CONNECTION

Описывает тип подключения к базе данных \(СУБД\), определяет используемый для подключения к СУБД драйвер. Может принимать одно из двух значений \(для проверенных СУБД\):

* `pgsql` — будет использоваться драйвер СУБД PostgreSQL;
* `mysql` — будет использоваться драйвер СУБД MySQL/MariaDB.

### APP\_DB\_HOST

Адрес хоста сервера СУБД. Может принимать значения:

* IPv4-адрес \(например, `127.0.0.1`\);
* URL \(например, `localhost`\).

Для PostgreSQL здесь должно быть указано значение адреса кластера СУБД. По умолчанию для локальной инсталляции используется адрес `127.0.0.1`.

### APP\_DB\_PORT

Сетевой порт кластера СУБД \(для PostgreSQL\) or server \(for MySQL\).

По умолчанию PostgreSQL использует порт кластера `5432`.

### APP\_DB\_NAME

Имя базы данных. Должна быть предварительно создана на сервере СУБД.

### APP\_DB\_USERNAME

Имя пользователя для подключения к БД, имеющему полные права на чтение/запись данных в указанную в параметре `APP_DB_NAME` базу данных. Данный пользователь будет использоваться для всех подключений приложений к БД.

### APP\_DB\_PASSWORD

Пароль пользователя, указанного в `APP_DB_USERNAME`.

### SUPER\_LOGIN

Логин пользователя приложения МИС Медкей, который должен иметь полномочия суперпользователя \(доступ ко всем функциям системы\), игнорируя настроенный ACL.

### SUPER\_PASSWORD

Пароль пользователя, указанного в `SUPER_LOGIN`.

### APP\_TYPE\_KEY

Тип первичных ключей записей в таблицах БД приложения: biginteger \(64 бита\) и UUID \(строка с глобальным идентификатором\). Параметр может принимать следующие значения:

* `bigint` — для целочисленных идентификаторов;
* `uuid` — для UUID \(GUID\) идентификаторов.

Внимание! Данный параметр должен быть задан _до_ развёртывания БД приложения. В дальнейшем не может быть изменён. Изменение значения параметра для ранее развёрнутого приложения гарантированно приведёт к его _неработоспособности_.

Мы рекомендуем использовать идентификаторы `bigint`.

### WIDGET\_LOADER\_URL

URI with starting slash of widget loader. By default use `/ui/widget-loader/factory`.

Can be changed only in development purposes. For production use default value.

### APP\_TITLE

Application title, which used at the top side of menu and at login form. Can be overwritted by parameter set in user interface.

You can set here any line of text you want to see in your UI.

### JOB\_TIMEOUT

Timeout for background workers. By default `1200`, but can be increased.

### AUTH\_WITH\_EMPLOYEE

Can be `true` or `false`. If you want to disable login users without employee record — set value to `false` \(production value\).

If you have service users without employee records — set this value to `true` to enable their authentication ability.

### LANGUAGE

Default application language. Can be overriden by default language param, which can be set at UI. It will be used for all users, which haven't set their personally preferred language.

Value can be:

* `ru` - for russian language;
* `en` - for english language.



