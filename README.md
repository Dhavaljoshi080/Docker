# Docker

## Create insfrastructure 
* Docker Installation on AWS instace 
  https://www.ktexperts.com/how-to-install-docker-in-amazon-linux-machine/
* Pull Mongo and MongoExpress images from docker.hub
```
$ docker pull mongo
$ docker pull mongo-express
```
* Check available images 
```
$ docker images
```
* Now need to connect both images throuth network port
  Check available ports
```
$ docker network ls
```
* create network called mongo-network
```
$ docker create network mongo-network
```
* Now can run containter however we can specify few things like Env ver, container name, port and so on ( Enviornmental variable can get it from docker.hub/mongo )
```
$ docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo
```
* Do the same thing for image mongo-express
```
$ docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express
```

