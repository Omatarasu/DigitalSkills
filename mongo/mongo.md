Import to pc from local db in docker container
---
     mongodump \
     --host=localhost:27017 \
     --db=database \
     --username=root \
     --config=mongo.txt \
     --authenticationDatabase=admin \

Export to azure cosmosDB
---
    mongorestore  \
		--host=omatarasu.mongo.cosmos.azure.com

# Connect And Find Data
Connect as admin
> mongosh/mongo "mongodb+srv://username:password@cluster.ru/admin"

Connect as admin and create db
> mongosh/mongo "mongodb://username:password@cluster.ru:27017/somedb?authSource=admin"

If connect to mongo in azure
> mongosh/mongo "mongodb://username:password@cluster.ru/db?ssl=true"

