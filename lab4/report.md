University: ITMO University

Faculty: FICT

Course: Introduction in routing

Year: 2022/2023

Group: K33212

Author: Gomzyakov Alexander

Lab: Lab4

Date of create: 27.12.2022

Date of finished: 12.01.2023
# Лабораторная работ №4 "Эмуляция распределенной корпоративной сети связи, настройка iBGP, организация L3VPN, VPLS" #

## Цель работы ##
Изучить протоколы BGP, MPLS и правила организации L3VPN и VPLS.
## Ход работы ##
### Первая часть ###
Воспользуемся текстом файла lab4.yml для развертывания сети
![изображение](https://user-images.githubusercontent.com/71012423/212117020-e2cb7938-85f4-487e-8349-4ad6d5456016.png)
1. Роутер (R01.NY)

![изображение](https://user-images.githubusercontent.com/71012423/212127373-2866a031-f88b-4ad8-b53c-90acbe648b48.png)

2. Роутер (R01.LND)

![изображение](https://user-images.githubusercontent.com/71012423/212121882-02c4a011-cc6d-4634-b045-a203af462dc3.png)

3. Роутер (R01.LBN)

![изображение](https://user-images.githubusercontent.com/71012423/212122801-fe3ce92a-3cfe-4075-a257-b3acf566dd68.png)

4. Роутер (R01.HKI)

![изображение](https://user-images.githubusercontent.com/71012423/212123728-26b0ee5a-cfa4-4b37-a09c-09cb730994e4.png)

5. Роутер (R01.SVL)

![изображение](https://user-images.githubusercontent.com/71012423/212129348-584e3627-2ce6-49fa-afa3-acaba5e6ba7e.png)

6. Роутер (R01.SPB)

![изображение](https://user-images.githubusercontent.com/71012423/212127517-b18e0a80-a86b-4c68-8f7d-7606c35c37cd.png)

### Пинг VRF ###

![изображение](https://user-images.githubusercontent.com/71012423/212136312-1dffafc8-8284-46e5-a333-c8b13f3e186b.png)

### Проверка BGP и VRF ###
![изображение](https://user-images.githubusercontent.com/71012423/212134563-a08574f5-232b-49b3-bbdc-2d2f2d18f6ff.png)

![изображение](https://user-images.githubusercontent.com/71012423/212134590-6424bc0a-7fa4-4590-9dea-cbbc51db55f4.png)

![изображение](https://user-images.githubusercontent.com/71012423/212134787-07a4a3ea-08ba-40a0-8c85-24824614a054.png)

## Вторая часть ##
Первым делом разбираем VRF  на R01.NY; R01.SPB; R01.SVL
