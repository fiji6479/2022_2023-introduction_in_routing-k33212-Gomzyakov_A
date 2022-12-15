University: ITMO University

Faculty: FICT

Course: Introduction in routing

Year: 2022/2023

Group: K33212

Author: Gomzyakov Alexander

Lab: Lab3

Date of create: 12.12.2022

Date of finished: 17.12.2022
# Отчет по лабораторной работе №3 "Эмуляция распределенной корпоративной сети связи, настройка OSPF и MPLS, организация первого EoMPLS" #

## Цель работы ##
Изучить протоколы OSPF и MPLS, механизмы организации EoMPLS.
## Ход работы ##
Воспользуемся текстом файла lab3.yml для развертывания сети

![изображение](https://user-images.githubusercontent.com/71012423/207977783-953255ac-dcc4-4d27-8e57-d202381ffa4b.png)

После этого настроим каждое устройство в нашей сети:

1) Роутер (R01.NY)

![изображение](https://user-images.githubusercontent.com/71012423/207978004-7b0b796e-b0a6-4d3c-bfa3-edded0e1a1d9.png)

2) Роутер (R01.LND)

![изображение](https://user-images.githubusercontent.com/71012423/207978137-d35659f4-7954-4f40-84b7-f5af478f8c16.png)

3) Роутер (R01.HKI)

![изображение](https://user-images.githubusercontent.com/71012423/207978258-7fde764c-eeb0-4a52-9525-f7386754ce5f.png)

4) Роутер (R01.LBN)

![изображение](https://user-images.githubusercontent.com/71012423/207978348-aa486be5-608d-41ba-9942-27444131e854.png)

5) Роутер (R01.MSK)

![изображение](https://user-images.githubusercontent.com/71012423/207978419-e28e47e5-b478-49c7-85fb-c46252f51b69.png)

6) Роутер (R01.SPB)

![изображение](https://user-images.githubusercontent.com/71012423/207978515-46b1b1d9-1593-483a-8ae2-f8d6c579179f.png)

7) Сервер (SGI_Prism)

![изображение](https://user-images.githubusercontent.com/71012423/207978762-4c1ed703-1c28-4e76-80b1-6cabed4091e1.png)

8) Компьютер (PC1)

![изображение](https://user-images.githubusercontent.com/71012423/207978817-0794ee5c-ecd4-442c-9655-0e1fb1e9e1cd.png)

После этого проверим таблицу маршрутизации на роутере с помощью команды "mpls forwarding-table print":

![изображение](https://user-images.githubusercontent.com/71012423/207979174-7ef29782-1170-4866-9e84-7df5b57c1beb.png)

Также проверим информацию об mpls отметках с помощью команды "tool trace ip-R01.SPB":

![изображение](https://user-images.githubusercontent.com/71012423/207979726-8b2b34c7-caad-44f7-9e58-f8c0014f4a6f.png)

Осталось только поменять логин и пароль у роутера.

![изображение](https://user-images.githubusercontent.com/71012423/207980403-b71ecc68-83d8-4d0f-8dfa-c815d4ca58ea.png)

## Вывод ##
В ходе выполнения лабораторной работы №3, мы изучили и научились использовать OSPF, MPLS и EoMPLS.В итоге мы получили рабочую связь для компании "RogaIKopita Games".



