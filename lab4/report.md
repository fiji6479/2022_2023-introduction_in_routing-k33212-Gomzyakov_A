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

Также поменяем логин и пароль у R01.NY

![изображение](https://user-images.githubusercontent.com/71012423/212144646-16aff6ca-a2c7-402b-bd07-dc1f04af2825.png)

## Вторая часть ##
Первым делом разбираем VRF на R01.NY; R01.SPB; R01.SVL. Далее на этих роутерах настроили VPLS. Также настроили конфигурацию PC1; PC2; PC3. 

1. Роутер (R01.NY)

![изображение](https://user-images.githubusercontent.com/71012423/212158238-e3e65dc4-35df-4ab3-b5de-23640e3c0481.png)

2. Роутер (R01.SVL)

![изображение](https://user-images.githubusercontent.com/71012423/212158286-62035d15-ab7e-48e8-8960-8df64c6bac23.png)

3. Роутер (R01.SPB)

![изображение](https://user-images.githubusercontent.com/71012423/212158318-27c4b0bc-82ee-4d50-a77e-5be50cfa8a4c.png)

4. PC1

![изображение](https://user-images.githubusercontent.com/71012423/212158515-2ddf00d5-7008-4991-a16d-58088b1d6f5e.png)

5. PC2

![изображение](https://user-images.githubusercontent.com/71012423/212158644-b9a02ddd-246b-4388-834b-b9b3dfef0cdf.png)

6. PC3

![изображение](https://user-images.githubusercontent.com/71012423/212158590-60984cd3-e534-45eb-aa89-f7c865c36eeb.png)

### Проверим связь компьютеров ###
![изображение](https://user-images.githubusercontent.com/71012423/212160075-7803633f-300e-41a9-aa07-2ea19953b08a.png)

![изображение](https://user-images.githubusercontent.com/71012423/212161315-72cedda7-9006-480c-91c2-aa83402ff1c0.png)

## Вывод ##
В ходе выполнения лабораторной работы №4, мы изучили BGP, MPLS и правила организации L3VPN и VPLS.В итоге мы получили рабочую сеть для компании "RogaIKopita Games".
