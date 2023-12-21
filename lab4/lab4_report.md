University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2023/2024
Group: K4111c
Author: Gabdrashitov Rinat Ramilevich
Lab: Lab3
Date of create: 21.12.2023
Date of finished: -.12.2023

## Лабораторная работа №4 "Сети связи в Minikube, CNI и CoreDNS"

### Описание
Это последняя лабораторная работа в которой мы познакомимся с сетями связи в Minikube. Особенность Kubernetes заключается в том, что у него одновременно работают underlay и overlay сети, а управление может быть организованно различными CNI.

### Цель работы
Познакомиться с CNI Calico и функцией IPAM Plugin, изучить особенности работы CNI и CoreDNS.

### Ход работы
- Запускаем minikube с устанволенным плагином Calico и двумя нодами.

![start](screens/start.png)
![info](screens/info2.png)

- Присвоим запущенным нодам метки варианты

![c](screens/change_variant.png)

- Создаем файл манифеста для назначения пула IP узлам на основе их меток
![ippool1](screens/ippool.png)

- Удаляем дефолтный Ippools и создаем свои
![ippool2](screens/del.png)
![v](screens/variants.png)

- Создаем манифест из 2 лр и запускаем на 8000 порту приложение
![a1](screens/app1.png)
![a2](screens/app2.png)

- Переменные container name и container ip изменяются в зависисмости от пода в который попал запрос
![web1](screens/web1.png)

- Чтобы убедиться в этом удалим под в который попали и запустим снова

![web1](screens/web2.png)

Можно заметить что эти значения изменились

На специальной панели можно просматривать состояния
![d](screens/dashboards0.png)
![d](screens/dashboards.png)

получаем айпи каждого пода
![i](screens/info.png)

Заходим на под, имеющий ip адрес 192.168.0.65 и имя itdt-contained-frontend-67ff5867b8-pzqwb, узнаем fqdn второго пода и производим команду ping
![i](screens/ping.png)
![i](screens/traceroute.png)

# Схема

![schema](screens/schema.png)