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
