Place any SQL files you want ran on the first spin up of the database.

Note, you wull need to remove the docker volume completely for these to run again on the next spin up 

`docker volume prune` -> this will remove every volumn

Or 

1) `docker volume ls` to get a list of all volumnes
2) Fine the name of the volume you need to delete
3) `docker volume rm <volume_name> 