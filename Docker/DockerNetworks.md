

> #### Docker Networking
  - USECASE1: Container1 app talking to Container2 app
  - USECASE2: conainter1 app talking to external service served by physical or virtual machine
 
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
