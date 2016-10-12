# Docker Cheat Sheet
This is a quick cheat sheet for docker commands!

### Images
These are templates for Containers.

| Action | Command |
|--------|---------|
| List All | docker images | 
| Import | docker import image.tar.gz |
| Build | docker build |
| Create Image from Container | docker commit |
| Remove | docker rmi image_name |
| Remove All | docker rmi $(docker images -q) |
| Remove Force | docker rmi image_name -f |

### Containers
These are Virtual Machines.

| Action | Command |
|--------|---------|
| List All | docker ps -a |
| List Running | docker ps |
| Create | docker create |
| Run | docker run container_name |
| Rename | docker rename container_name new_name |
| Stop | docker stop container_name |
| Stop All | docker stop $(docker ps -a -q) |
| Restart | docker restart container_name |
| Pause | docker pause container_name |
| Unpause | docker unpause container_name |
| Remove All | docker rm $(docker ps -a -q) |
| Remove Force | docker rm container_name -f |
| Connect to Running | docker attach container_name |
| Connect Dynamically | docker exec -it container_name sh |
| | docker exec -it container_name /bin/bash |
| **Info** | |
| Get Logs | docker logs |
| Get Info | docker inspect |
| Show Events | docker events |
| Show Public Facing Port | docker port |
| Running Processes | docker top |
| Resource Usage | docker stats |
| Changes in Filesystem | docker diff |

### Networks


### Repository
| Action | Command |
|--------|---------|
| Login | docker login |
| Logout | docker login |
| Search | docker search |
| Pull | docker pull |
| Push | docker push |
