# Docker
All Docker fundamental cheatsheet from Cliff Kwok

Start the docker
======================
# very first command
docker

# Check version
docker --version

# Image 
docker pull <<image name>>     # download images
docker images                  # check existing images in docker

# Run
docker run <<image name + tag>>
docker run -d <<image name + tag>>               # means that a Docker container runs in the background of your terminal
docker run -d -p 8080:80 <<image name + tag>>   # My computer (host port) is 8080 which can access container 80
docker run -d -p 8080:80 -p 3000:80 <<image name + tag>>  # 2 local port to same container port
docker run --name <<container name>> -d -p 8080:80 -p 3000:80 <<image name + tag>>
docker run --name <<container name>> -v $(pwd):/root/docker -d -p 8080:80 -p 3000:80 <<image name + tag>>
  

# Container
docker container ls            # check running container
docker ps                      # check running container (quick way)
docker ps -a                   # check all contianer (show all)
docker stop <<container id>>
docker stop <<container name>>
docker start <<container name>>
docker rm <<container id>>    # remove individual container
docker ps -aq                 # show all container id
docker rm $(docker ps -aq)    # delete all exisiting container
docker rm -f $(docker ps -aq)    # delete all exisiting container
  
! # every time start a container, it create new container id

# Quit
Control + C                    # quit when in status of running container
Control pq

# Exec
docker exec -it <<container name>> bash
  
# Create file
touch about.html



