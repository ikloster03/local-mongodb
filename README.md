# Local mongodb

## Start/stop

```sh
docker compose up -d
docker compose rm -s
```

## Restore dump

```sh
# 1. copy your dump to ./import folder
cp -r path_to_source/ path_to_destination/
# 2. look at you container's name
docker compose ps 
# or 
docker ps
# 3. enter to mongo container bash 
docker exec -it <container_name> bash
# 4. run db restoring
mongodump <uri> -o=./dump
mongorestore dump/
```
