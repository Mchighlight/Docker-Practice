# About
Build, test, and deploy Docker application with Kubernetes
# Environment
Because I am a Windows Home user, i will not be able to install the Docker for Windows Desktop edition . Luckily, the newer Docker Desktop verstion does not require VirtualBox to run Docker . 
Running the docker via Docker Toolbox is one of the great options . Here is the Docker toolbox download link https://docs.docker.com/toolbox/toolbox_install_windows/
# Learning Note
## Part one basic docker command
### Images and Containers
check existed images
```cmd
docker images 
```
create images( busybox for example )
```cmd
docker create -it --name busybox busybox
```
delete images
```cmd
docker rmi [OPTIONS] IMAGE [IMAGE...]
```
check operated container
```cmd
docker ps
```
check all current containers( includes of terminated container )
```cmd
docker ps -a
```
run container
```cmd
docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
```
start container
```cmd
docker start [OPTIONS] CONTAINER [CONTAINER...]
```
stop container
```cmd
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```
restart container
```cmd
docker restart [OPTIONS] CONTAINER [CONTAINER...]
```
delete container
```cmd
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```
`--volumes , -v` adding previous variable will delete the volume of container
enter container
```cmd
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
docker exec -it <Container ID> bash
```
check logs
```cmd
docker logs [OPTIONS] CONTAINER
```
`--follow` , `-f`  ,  Follow log output
check container resource
```cmd
docker stats [OPTIONS] [CONTAINER...]
```
 `docker stop` : process level。

 `docker pause`: container level。
 
docker tag
```cmd
docker tag 0e5574283393 henry/botty:1.0
```

save image as tar file
```cmd
docker save redis > redis.tar
```

load image
```cmd
docker load < busybox.tar
```
check history of image
```cmd
docker history [OPTIONS] IMAGE
```
stop all currently operated container
```cmd
docker stop $(docker ps -q)
```
### Volumnes
volume 的內容存在於 container 之外。
check volumes

```cmd
docker volume ls [OPTIONS]
```

create volumes

```cmd
docker volume create [OPTIONS] [VOLUME]
```

delete volumes

```cmd
docker volume rm [OPTIONS] VOLUME [VOLUME...]
```

check specific info of value

```cmd
docker volume inspect [OPTIONS] VOLUME [VOLUME...]
```

remove unused volumn

```cmd
docker volume prune [OPTIONS]
```
### network TODO: have not learned yet

## Part two Docker compose

