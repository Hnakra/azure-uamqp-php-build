# AMQP PHP BUILD

Проект, содержащий образ для запуска и тестирования AMQP PHP клиента.

Реализован на базе https://github.com/vsouz4/azure-uamqp-php

Вам потребуется Windows 10/11 и установленный Docker Desktop.

## Инструкция по запуску
### 1. Запуск AMQP брокера (Windows 10)
Скачайте [AMQ Broker 7.11.6](https://access.redhat.com/jbossnetwork/restricted/listSoftware.html?product=jboss.amq.broker), а также запустите и протестируйте его по [инструкции](https://access.redhat.com/documentation/ru-ru/red_hat_amq_broker/7.11/html-single/getting_started_with_amq_broker/index)

### 2. Сборка и запуск клиента (Ubuntu 18.04 в docker контейнере)

2.1. Склонируйте проект в любое удобное место
```
git clone https://github.com/Hnakra/azure-uamqp-php.git
```
2.2 Запустите его, в корне проекта выполнив команду
```
docker-compose up -d
```
2.3 На основе файла parameters.php.dist создайте файл parameters.php со своими параметрами подключения к брокеру.

2.4 Зайдите внутрь контейнера azure-uamqp-php-build любым удобным для вас способом, например:
```
docker exec -it azure-uamqp-php-build-amq-client-1 bash
```

2.5 Перейдите в директорию с примерами
```
cd /var/www/html/example
```
2.6 Тестируйте :)
```
php consumer.php
```
```
php producer.php
```