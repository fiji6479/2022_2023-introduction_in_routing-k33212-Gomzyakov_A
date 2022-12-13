University: ITMO University

Faculty: FICT

Course: Introduction in routing

Year: 2022/2023

Group: K33212

Author: Gomzyakov Alexander

Lab: Lab2

Date of create: 6.12.2022

Date of finished: 13.12.2022
# Отчет по лабораторной работе №2 "Эмуляция распределенной корпоративной сети связи, настройка статической маршрутизации между филиалами" #

## Цель работы ##
Ознакомиться с принципами планирования IP адресов, настройке статической маршрутизации и сетевыми функциями устройств.
## Ход работы ##
Воспользуемся текстом файла lab2.yml для развертывания сети
![изображение](https://user-images.githubusercontent.com/71012423/207320186-1fa29d99-a27a-492b-bd8a-cad1cdfe3a9b.png)

После этого настроим каждое устройство в нашей сети:

1)Роутер (RO1.MSK)

![изображение](https://user-images.githubusercontent.com/71012423/207320587-797c70cd-40e8-4b46-9f4c-1ff3d7210f13.png)

2)Роутер (RO1.FRT)

![изображение](https://user-images.githubusercontent.com/71012423/207320872-4d1fc6ea-477d-4fa5-9f24-87aebd4906de.png)

3)Роутер (RO1.BRL)

![изображение](https://user-images.githubusercontent.com/71012423/207321001-65f70180-86f4-4828-b231-6bcb58d1cd7d.png)

4)Компьютер (PC1)

![изображение](https://user-images.githubusercontent.com/71012423/207321132-7c97c310-d9e4-4c72-b583-40d7d32776a1.png)

5)Компьютер (PC2)

![изображение](https://user-images.githubusercontent.com/71012423/207321252-eee781ae-d113-4eb0-ae17-c47eb2e14a1f.png)

6)Компьютер (PC3)

![изображение](https://user-images.githubusercontent.com/71012423/207321342-c7afb1a8-4228-4ef3-9e27-bf7fb1283f7b.png)

После этого на каждом из трёх компьютеров узнаем ip с помощью команды "ip address print" и пропингуем их.

![изображение](https://user-images.githubusercontent.com/71012423/207322575-b6b05a64-f852-44d6-9993-7295624f12aa.png) 
![изображение](https://user-images.githubusercontent.com/71012423/207323316-9ccd81a9-977e-4d0e-a70c-ee31b19abe71.png)
![изображение](https://user-images.githubusercontent.com/71012423/207322668-1f5c8a25-a081-40c8-aa61-4797144ba2bc.png)
![изображение](https://user-images.githubusercontent.com/71012423/207322739-ba3374ca-6e74-4ad8-8c21-e5826f4ad01c.png)
![изображение](https://user-images.githubusercontent.com/71012423/207322824-872e07b3-337c-4360-ada4-fb1d87c10009.png)
![изображение](https://user-images.githubusercontent.com/71012423/207323454-0d292e56-cf7f-46f9-b75d-d0d1043c92cb.png)

Как мы можем заметить, все компьютеры пингуются, следовательно все настроенно правильно.
Теперь поменяем пароль и логин у Роутера (RO1.MSK)

![изображение](https://user-images.githubusercontent.com/71012423/207323956-bf4d2b0c-c4cc-4f85-804a-92e2cd39df57.png)
![изображение](https://user-images.githubusercontent.com/71012423/207323971-17ca8812-b689-4b68-830f-e3a16f2b1660.png)

## Вывод ##
В ходе выполнения работы было создана связь трёх геораспределенных офисов.Также я настроил статистическую маршрутизацию,создал DHCP-сервера на роутерах в сторону клиентских устройств.И на последок поменял логин и пароль у ротуера
