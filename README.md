# docker-node-python
docker basic command with node and python

# 1) Create appropriate images for both apps (two separate images!).
     go to folder and run this command, it will create image
     docker build .
     
     To check image created or not, run this command,
     docker ps or docker ps -a
     
# 2) Launch a container for each created image
   # node
   docker run -p 3000:3000 82b12de5075b
   # python
   docker run -it 7fff0493f14a
   
   -it is open terminal with interactive mode.

   To stop the container,
   docker stop thirsty_moore
   
   To restart the container, 
   docker start -it thirsty_moore

# 3) Re-build the images and container - this time with names and tags assigned to them and removed automatically when stopped.

    # node
    docker build -t assgiment:node .
    docker run -p 3000:3000 --rm --name node assgiment:node
    
    #note
    -t for tag
    --rm for removed automatically when container is stopped
    
    # python
    docker build -t assgiment:python .
    docker run -it --rm --name python assgiment:python
    
# 4) Clean up (remove) all stopped (and running) containers.

   remove container,
   docker rm node python
   
   remove images,
   docker rmi 7fff0493f14a 82b12de5075b
   
# useful commands

   to check stopped container,
   docker ps -a
   
   stop the container,
   docker stop CONTAINER-NAME
   
   start the container,
   docker start CONTAINER-NAME
   
   start the container with interactive mode,
   docker start -i CONTAINER-NAME
   
   to check logs,
   docker logs -f CONTAINER-NAME
   
   run container with detach mode(background)
   docker run -p 3000:3000 -d CONTAINER-NAME
   
   run container with detach mode(background) and remove after stopping the container
   
   docker run -p 3000:3000 -d --rm CONTAINER-NAME
   
   start container with attach mode
   
   docker attach CONTAINER-NAME
   
   # to get help
   docker COMMAND --help
   
   ex:- docker attach --help, docker start --help, docker logs --help
    

