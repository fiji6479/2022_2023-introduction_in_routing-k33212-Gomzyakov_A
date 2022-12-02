University: ITMO University

Faculty: FICT

Course: Introduction in routing

Year: 2022/2023

Group: K33212

Author: Gomzyakov Alexander

Lab: Lab1

Date of create: 15.11.2022

Date of finished: 2.12.2022
# Отчет по лабораторной работе №1 "Установка ContainerLab и развертывание тестовой сети связи" #

## Цель работы ##

Ознакомиться с инструментом ContainerLab и методами работы с ним, изучить работу VLAN, IP адресации и т.д.
## Ход работы ##
Воспользуемся текстом файла lab1.yml для развертывания сети
![изображение](https://user-images.githubusercontent.com/71012423/205237334-9032d62c-55c2-4ed5-ad51-5a2696d786d2.png)


После этого настроим каждое устройство в нашей сети:

1)R01.TEST


![изображение](https://user-images.githubusercontent.com/71012423/205237640-908e0ca9-5b92-41d4-9331-64476ece3908.png)


2)SW01.l3.01.TEST


![изображение](https://user-images.githubusercontent.com/71012423/205237853-07d12200-b0c2-4366-bb1a-3fe9b9d93d0a.png)


3)SW02.l3.01.TEST


![изображение](https://user-images.githubusercontent.com/71012423/205237919-d7077704-5a84-492d-bdc5-7d17400050b0.png)


4)SW02.l3.02.TEST


![изображение](https://user-images.githubusercontent.com/71012423/205238022-d375507c-c764-4a2d-8c23-74c0da8a8c9b.png)


После этого на каждом из двух свитчей узнаем ip с помощью команды "ip address print" и пропингуем их. 

![изображение](https://user-images.githubusercontent.com/71012423/205238395-b9bc3375-317d-4181-912e-a2604cbac90a.png)

![изображение](https://user-images.githubusercontent.com/71012423/205238415-a9a24dfc-b3de-4da5-8ba8-54c80e9eb4f4.png)

![изображение](https://user-images.githubusercontent.com/71012423/205238443-87b77edc-90ef-4bff-a172-0872f71a8fde.png)

![изображение](https://user-images.githubusercontent.com/71012423/205238459-365b62f5-8b0c-45df-ae75-2d91d555b283.png)

И в заключении поменяем логин и пароль у роутера R01

![изображение](https://user-images.githubusercontent.com/71012423/205238748-67c7c43b-2d46-4b69-9216-2b5db513fe6b.png)

![изображение](https://user-images.githubusercontent.com/71012423/205238783-6284ef6c-5036-4ed4-b9a9-38665cd24b2a.png)

## Вывод ##
В ходе лаборраторной работы с помощью файла "Конфигурация сети" была развернута сеть из роутера, трех коммутаторов и двух пк. Также мы поменяли пароли и логин у роутера и свитчей, настроили vlan и dhcp-server для раздачи ip-address. А наши успешные пинги только подтвердили работоспособность сети.

