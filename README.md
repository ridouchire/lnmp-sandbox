LNMP - Linux & Nginx & Mysql & PHP-fpm sandbox
=====

Установка
---------
0. Требуется установленный в системе docker и docker-compose. Воспользуйтесь документацией к вашему дистрибутиву и пакетному менеджеру для установки данных зависимостей.
1. `git clone git@github.com:ridouchire/lnmp-sandbox.git`
2. `cd lnmp-sandbox`
3. `docker-compose up -d --build`
4. PROFIT! Теперь можно сходить по адресу http://localhost:9999 и увидеть, что всё работает. Например, создать в `./public` файл `index.php` с таким содержимым:
```php
<?php

phpinfo();
```
и убедится, что связка nginx и php-fpm работает корректно.

Информация
----------

* Для php установлены модули mysqli, pdo_mysql, zip и curl, а также composer для управления зависимостями вашего проекта. Например, запуск composer:
```bash
docker exec sandbox-php composer install
```
это запустит composer для вашего проекта в `./public`. Конечно, сам проект и его файлы там уже должны быть размещены.

* Доступ к mysql-консоли
```bash
docker exec -it sandbox-db bash
mysql -uroot -proot
```
и всё! Можно выполнять SQL-запросы.
