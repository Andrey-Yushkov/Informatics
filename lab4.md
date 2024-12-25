## Создание образа

### 1. Создаем Dockerfile со следующим содержимом:

![image](https://github.com/user-attachments/assets/b74f3b51-05b5-43bd-b675-32c8031c1dc1)
### 2. Строим образ "aafire-image" и запускаем его:
```
  sudo docker built -t aafire .
  sudo docker run -it aafire /usr/bin/aafire
```
![image](https://github.com/user-attachments/assets/d9adff3b-fa32-40a3-bcd2-132c9c7f4f91)

###3) Изменил Dockerfile и добавил во вторую строку команду скачивания пакета с ping
```
  FROM ubuntu:latest
  RUN apt-get update && apt-get install -y libaa-bin
``` 
### 4) Собрал образ и запустил 2 контейнера, назвала их aafire1 и aafire2
```
  sudo docker build -t aafire_ping .
  sudo docker run -it --name aafire1 aafire_ping
  sudo docker run -it --name aafire2 aafire_ping
```

### 5) Создадим два новых контейнера, дописав sleep infinity, чтобы контейнер не останавливал свой процесс:
```
sudo docker run -d --name aafire1 aafire-image sleep infinity
sudo docker run -d --name aafire2 aafire-image sleep infinity
```


### 6) Создим сеть "myNetwork" и подключаем к ней контейнеры:
```
sudo docker network create myNetwork
sudo docker network connect myNetwork aafire1
sudo docker network connect myNetwork aafire2
```

### 7) Проверяем ping для каждого контейнера:

![image](https://github.com/user-attachments/assets/a52daead-078c-4905-92e7-95018380fc7a)
![image](https://github.com/user-attachments/assets/e0b73e16-a8b3-427e-870f-160b34a48505)
