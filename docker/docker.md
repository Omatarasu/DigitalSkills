
#### Посмотреть все контейнеры
> docker ps -a 

#### Включить в фоновом режиме
> docker run -d nginx 

#### Проброс портов
> docker run -p 1000:1001 (local:docker) nginx

#### Имя контейнера
> docker run --name some-name nginx

#### Посмотреть логи 
> docker logs some-name/id

#### Войти в контейнер
> docker exec -it some-name/id /bin/bash

#### Посмотреть сети
> docker network ls 

---
NETWORK
docker network create mongo-net # создание сети
---

MONGO
---
	docker run -d \
	-p 27017:27017 \
	-e MONGO_INITDB_ROOT_USERNAME=root \
	-e MONGO_INITDB_ROOT_PASSWORD=toor \
	--network mongo-net \
	--name mongodb mongo
---

MONGO-EXPRESS
---
	docker run -d -p 8081:8081 -e \
	ME_CONFIG_MONGODB_ADMINUSERNAME=root -e \
	ME_CONFIG_MONGODB_ADMINPASSWORD=toor -e \
	ME_CONFIG_MONGODB_SERVER=mongodb \
	--net mongo-net \
	--name mongo-express \
	mongo-express


BUILD PUSH TO ACR
---
#### Создание image из Dockerfile
  > docker build -t my-app:1.0 . 

#### Логин в azure
  > az acr login --name myacr # логин в ACR

#### Тегировать
  > docker tag my-app:1.0 myacr.azurecr.io/my-app:v1

#### Закидование в azure ACR
  > docker push myacr.azurecr.io/my-app:v1 
 

DOCKER VOLUMES 
---
1. docker run -v /home/mount/data:/var/lib/mysql/data mariadb
2. docker run -v /var/lib/mysql/data # in /var/lib/docker
3. docker run -v name:/var/lib/mysql/data # именованный, но также в /var/lib/docker