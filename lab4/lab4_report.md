# Лабораторная работа №4 "Базовая 'коммутация' и туннелирование используя язык программирования P4"

University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Network programming]([https://github.com/itmo-ict-faculty/introduction-in-routing](https://itmo-ict-faculty.github.io/network-programming/))
Year: 2024/2025
Group: K3323
Author: Danilenko Dmitriy Alexandrovich
Lab: Lab4
Date of create: 01.06.2025
Date of finished:

## Ход работы

### Basic

Схема для этого задания выглядит следующим образом

![schema](files/schema1.png)

Допишем файл [basic.p4](files/basic.p4)

Опишем логику разбора заголовков в парсере

![1.1](files/1.1.png)

Опишем логику маршрутизации ipv4-пакета - указанием порта, заменой адресов и уменьшением ttl

![1.2](files/1.2.png)

В deparser допишем добавление заголовка ipv4

![1.3.png](files/1.3.png)

Проверим работоспособность

![result1.png](files/result1.png)

### Basic tunneling

Схема для этого задания выглядит следующим образом

![schema2.png](files/schema2.png)

Опишем логику обработки заголовков туннелирования

![2.1](files/2.1.png)

Опишем таблицу с ключом и действиями, необходимыми для туннелирования, укажем стандартный размер и дефолтное действие

![2.2](files/2.2.png)

Опишем сценарии использования туннелирования и базовой коммутации

![2.3](files/2.3.png)

Не забудем добавить соответствующие заголовки

![2.4](files/2.4.png)

Проверим рабоспособность нашей сети и отправим сообщение на ip, соответствующему h2

![2.5](files/2.5.png)

Добавим id h2, но ip укажем другой ноды. В результате, благодаря туннелированию, пакет все-равно отправится на h2.

![2.6](files/2.6.png)
