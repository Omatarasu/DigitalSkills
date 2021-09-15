# Export And Import Data
## BSON
Import to pc
> mongodump --uri ""

Export to db
> mongorestore 	--uri ""
>		--drop dump

## JSON
Import to pc
> mongoexport 	--uri ""
>		--collection=collection name
>		--out=filename.json

Export to db
> mongoimport	--uri ""
>		--drop=filename.json
>		--collection filename

# Connect And Find Data
Connect as admin
> mongosh/mongo "mongodb+srv://username:password@cluster.ru/admin"

If connect to mongo in azure
> mongosh/mongo "mongodb://username:password@cluster.ru/db?ssl=true"

