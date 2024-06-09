

> #### Docker Networking (https://github.com/moby/libnetwork/blob/master/docs/design.md)
  - USECASE1: Containers running on single hosts talk to each other ( BRIDGE NETWORK )
  - USECASE2: Containers running on multiple hosts talk to each other ( OVERLAYS )
  - ![image](https://github.com/cskarthik22/Notes/assets/38231831/77664d89-09b0-40a2-aab3-6b6a5cfbfc97)

 
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
