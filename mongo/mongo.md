          wget https://downloads.mongodb.com/compass/mongodb-mongosh_1.0.6_amd64.deb 
          sudo chmod 0777 mongodb-mongosh_1.0.6_amd64.deb 
          sudo apt install ./mongodb-mongosh_1.0.6_amd64.deb


          wget https://fastdl.mongodb.org/tools/db/mongodb-database-tools-ubuntu1604-x86_64-100.5.0.deb
          chmod 0777 mongodb-database-tools-ubuntu1604-x86_64-100.5.0.deb
          sudo apt install ./mongodb-database-tools-ubuntu1604-x86_64-100.5.0.deb
Import to pc from local db in docker container
---
     mongodump \
     --host=localhost:27017 \
     --db=database \
     --collection=mycollection \ 
     --username=root \
     --config=mongo.txt \
     --authenticationDatabase=admin \

mongo.txt: 
> password: toor

Export to azure cosmosDB
---
    mongorestore  \
    --host=root.mongo.cosmos.azure.com:10255 \
    --db=database \
    --collection=mycollection \
    --username=root \
    --config=azure.txt \
    --authenticationDatabase=admin \
    --ssl \
    --writeConcern="{w:0}" \
    file.bson \
    
 azure.txt:
 > password: toor

Connect And Find Data
---
Connect as admin

     mongosh/mongo "mongodb+srv://root:toor@localhost/admin"

Connect as admin to another db

     mongosh/mongo "mongodb://root:toor@localhost:27017/somedb?authSource=admin"

If connect to mongo in azure

     mongosh/mongo "mongodb://root:toor@root.mongo.cosmos.azure.com/db:10255?ssl=true"

