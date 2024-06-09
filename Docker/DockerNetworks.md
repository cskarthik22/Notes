

> #### Docker Networking
  - ##### https://github.com/moby/libnetwork/blob/master/docs/design.md
  - ![image](https://github.com/cskarthik22/Notes/assets/38231831/77664d89-09b0-40a2-aab3-6b6a5cfbfc97)
> #### USECASE1: Containers running on single hosts talk to each other ( BRIDGE NETWORK )
  - #### Sandboxes are placed inside of containers to provide network connectivity
  - ![image](https://github.com/cskarthik22/Notes/assets/38231831/7daf6cb0-9bb3-4176-918d-313264d962d2)



 
- Container Networking Model --> libnetwork 

By default docker containers use bridge driver
- Each container has its own network stack
brctl show
docker run -it --net none alphine sh
