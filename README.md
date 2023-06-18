# vpn_ras
#Создаем Vagrantfile следующего содержания
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/37211359-8bed-4b32-9d1e-c9e879bc9ca5)
#Устанавливаем репозитирий и необходимые пакеты
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/18122a93-4fd9-4077-8ead-1056efbc559d)
#Переходим в директорию /etc/openvpn и инициализируем pki
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/cff3f767-5698-42d5-9ccf-44bf4725b14d)
#Сгенерируем ключи и сертификаты для сервера
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/71848472-6fcc-47de-9706-df4547b4e820)

![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/4d498340-c386-4e32-8956-b5c5f323e029)

![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/f3745fe0-0a4a-4631-966d-1cbf2aabcaae)


![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/d21b0514-cd53-4e8b-aa16-af7b2f725859)

#Сгенерируем сертификаты для клиента
![Снимок экрана от 2023-06-18 15-51-06](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/15af69d4-498a-4fcf-9ce5-f0b20d25f076)
#Создадим конфигурационный файл /etc/openvpn/server.conf
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/24e07dee-e3c0-48f0-a94e-ae74d0f4747e)

#Зададим параметр iroute для клиента
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/5656f572-fc4f-448b-8d15-2ad179b4b2fe)
#Запускаем openvpn сервер и добавляем его в автозагрузку
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/dac7ec61-9721-4a69-ad88-3aa697c768b0)
#Скопируем следующие файлы сертификатов и ключ для клиента на хост-
машину.

/etc/openvpn/pki/ca.crt
/etc/openvpn/pki/issued/client.crt
/etc/openvpn/pki/private/client.key
используя утилиту scp

![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/120c6e00-f083-4624-b343-6bf08a0c4cbb)


![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/02d38ad3-e82e-43d9-8c38-b37e76669237)

![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/5834bc5e-0220-4b7c-bf68-6bb0456a7941)

#Убедимся что файлы скопировались на хост.

![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/446eca61-cf69-427d-94e9-d44e64d86289)
 # Создаем файл client.conf следующего содержания
 ![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/00714f39-fa0c-4e9f-bafb-92e9852d3a24)
#Добавим маршрут что бы хост могу общаться с виртаульной машиной используя команду sudo route add -net 192.168.50.0 netmask 255.255.255.0 dev vboxnet1

![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/85466f56-d342-4d67-84d7-848268e62020)

#Проверим видят ли друг друга ОС. Как видно из скрина все прошло успешно
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/96934ef6-3755-4a94-974b-e65c8827fc55)
#Запустим vpnclient
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/ba8c2cf6-44f6-4cd4-88b2-82f7079d29f6)
#Проверим 
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/1d1ff0c8-ab3d-4a96-ab72-5073d4377b40)

#Как мы видим все успешно
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/d307d78a-6907-405c-b3ab-cfc7e32e060d)

# Таблица маршрутизации на хосте 
![image](https://github.com/AlexanderSerg-jun/vpn_ras/assets/85576634/361afbb2-645a-46cd-98ab-b26761d8e34d)







