Установка docker на ubuntu:
---
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - \
	sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \
	sudo apt-get update \
	apt-cache policy docker-ce \ 
	sudo apt-get install -y docker-ce \

	
#### Посмотреть все контейнеры
	
	docker ps -a 

#### Включить в фоновом режиме
	
	docker run -d nginx 

#### Проброс портов
	
	docker run -p 1000:1001 (local:docker) nginx

#### Имя контейнера
	
	docker run --name some-name nginx

#### Посмотреть логи 
	
	docker logs some-name/id

#### Войти в контейнер
	
	docker exec -it some-name/id /bin/bash

#### Посмотреть сети

	docker network ls 

#### Cоздание сети
	
	docker network create my-net 


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

	docker build -t my-app:1.0 . 

#### Логин в azure

	az acr login --name myacr # логин в ACR

#### Тегировать
 
 	docker tag my-app:1.0 myacr.azurecr.io/my-app:v1

#### Закидование в azure ACR
 
 	docker push myacr.azurecr.io/my-app:v1 
 

DOCKER VOLUMES 
---
	docker run -v /home/mount/data:/var/lib/mysql/data mariadb
	
	docker run -v /var/lib/mysql/data # in /var/lib/docker
	
	docker run -v name:/var/lib/mysql/data # именованный, но также в /var/lib/docker
