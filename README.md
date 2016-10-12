# Docker Cheat Sheet
This is a quick cheat sheet for docker commands!

### Images
These are templates for Containers.

| Action | Command |
|--------|---------|
| List All | `docker images` | 
| Build | `docker build` |
| Create Image from Container | `docker commit` |
| Import | `docker import image.tar.gz` |
| Remove | `docker rmi image_name` |
| Remove All | `docker rmi $(docker images -q)` |
| Remove Force | `docker rmi image_name -f` |

### Containers
These are Virtual Machines.

| Action | Command |
|--------|---------|
| List Running | `docker ps` |
| List All | `docker ps -a` |
| Create | `docker create` |
| Run | `docker run container_name` |
| Connect to Running | `docker attach container_name` |
| Connect Dynamically | `docker exec -it container_name sh` |
| | `docker exec -it container_name /bin/bash` |
| Rename | `docker rename container_name new_name` |
| Stop | `docker stop container_name` |
| Stop All | `docker stop $(docker ps -a -q)` |
| Restart | `docker restart container_name` |
| Pause | `docker pause container_name` |
| Unpause | `docker unpause container_name` |
| Remove All | `docker rm $(docker ps -a -q)` |
| Remove Force | `docker rm container_name -f` |
| Remove Old | `docker ps -a | grep 'weeks ago' | awk '{print $1}' | xargs docker rm` |
| Remove Stopped | `docker rm -v $(docker ps -a -q -f status=exited)` |
| Remove Dangling | `docker rmi $(docker images -q -f dangling=true)` |
| Kill | `docker kill container_name` |
| Kill Running | `docker kill $(docker ps -q)` |
| **Info** | |
| Get Logs | `docker logs` |
| Get Info | `docker inspect` |
| Show Events | `docker events` |
| Show Public Facing Port | `docker port` |
| Running Processes | `docker top` |
| Resource Usage | `docker stats` |
| Changes in Filesystem | `docker diff` |

### Networks
Talking to containers work great with ports but you can create networks too. There is also Docker Swarm to create more advanced networks.

| Action | Command |
|--------|---------|
| Create | `docker network create` |
| Remove | `docker network rm` |
| Connect | `docker network connect` |
| Disconnect | `docker network disconnect` |
| **Info** | |
| List | `docker network rm` |
| Inspect | `docker network inspect` |

Example:
```
# Create a Subnet for containers and the Gateway
docker network create --subnet 192.168.25.0/24 --gateway 192.168.25.0 superfly

# Run a container in the network
docker run -it --net superfly --ip 192.168.25.1 image_name

# Ping the container from another terminal
ping 192.168.25.1
```

### Repository
| Action | Command |
|--------|---------|
| Login | `docker login` |
| Logout | `docker login` |
| Search | `docker search` |
| Pull | `docker pull` |
| Push | `docker push` |
