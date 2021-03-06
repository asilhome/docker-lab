# docker v18.01.0-ce
https://docs.docker.com/get-started/

## projects
- [spring-boot](/spring-boot/README.md)
- [jenkins](/jenkins/README.md)

## installation
- windows 10
  - https://www.docker.com/community-edition#/download
- windows 7
  - https://docs.docker.com/toolbox/toolbox_install_windows/
  - don't install virtualbox, if already installed

## terminal
open `docker quickstart terminal (bash)`

### test run
```
$ docker run hello-world
```
## add/update port forwarding
- oracle vm virtualbox > running vm > settings > network > nat > advanced
  - host ip: <ipconfig>
  - host port
  - guest ip: <docker-machine ip>
  - guest port: <expose>

## signup
https://cloud.docker.com/

## container
## share image to repository
https://cloud.docker.com/
```
$ docker login
$ docker tag <image> <username>/<repository>:<tag>
```

### publish
```
$ docker push <username>/<repository>:<tag>
```

## commands
### check
```
$ docker -v  # version
$ docker version  # clien & server
$ docker ps  # list running containers
$ docker ps -a  # list all containers
$ docker info  # system-wide info
$ docker-machine ip
```
### image
- Dockerfile
```
$ docker pull <image>  # get image from public repo/registry
```
```
$ docker build -t <image> .  # and tag a name
```
```
$ docker image ls -a  # List all images on this machine
```
```
$ docker run -d -p 8080:8080 --name=<container> <image>  # give container name
$ docker run username/repository:tag  # from a registry
```
```
$ docker image rm <image>
$ docker image rm username/<image>:tag
$ docker image rm $(docker image ls -a -q)  # remove all images from this machine
```
goto `http://<docker-machine-ip>:8080`

### container
```
$ docker container ls -a  # running only
$ docker container ls -a  # plus not running
$ docker logs <container>  # see logs
$ docker exec -it <container> bash  # open bash in container
$ docker inspect <container>  # detail about container
```
```
docker start <container>
docker stop <container>
docker rm <container>
```

### house-keeping
```
$ docker system prune -a  # remove/cleanup images & containers
```
```
$ docker volume ls -f dangling=true  # check volumes not attach to container
$ docker volume prune
```
#### from docker
```
docker login  # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag  # Upload tagged image to registry
```

### network
```
docker network ls  # list networks
```

# other images
- https://github.com/mysql/mysql-docker
- oracle
- jboss fuse
- pentaho
