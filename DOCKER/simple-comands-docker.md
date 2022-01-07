Useful Docker Commands#
Create a container:

docker run CONTAINER --network NETWORK
Start a stopped container:

docker start CONTAINER NAME
Stop a running container:

docker stop
List all running containers

docker ps
List all containers including stopped ones

docker ps -a
Inspect the container configuration. For instance network settings and so on:

docker inspect CONTAINER
List all available virtual networks:

docker network ls
Create a new network:

docker network create NETWORK --driver bridge
Connect a running container to a network

docker network connect NETWORK CONTAINER
Disconnect a running container from a network

docker network disconnect NETWORK CONTAINER
Remove a network

docker network rm NETWORK
