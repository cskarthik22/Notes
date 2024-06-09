

> #### Docker Networking (https://github.com/moby/libnetwork/blob/master/docs/design.md)
  - USECASE1: Containers running on single hosts talk to each other ( BRIDGE NETWORK )
  - USECASE2: Containers running on multiple hosts talk to each other ( OVERLAYS )
 
- Container Networking Model --> libnetwork 

By default docker containers use bridge driver
- Each container has its own network stack
brctl show
docker run -it --net none alphine sh

docker network ls # by default it shows the below 3
 - brdige
 - host
 - null
docker netowrk create dev # creates a new dev network.
