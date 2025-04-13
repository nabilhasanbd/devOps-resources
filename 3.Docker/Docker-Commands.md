docker run nginx => Runs a container using the Nginx image, starting the web server.

docker ps => Lists all currently running containers.

docker ps -a => Lists all containers, including stopped ones.

docker stop "container-name" => Stops a running container with the specified name.

docker rm "container-name" => Removes a stopped container with the specified name.

docker images => Displays all Docker images available locally.

docker rmi nginx => Deletes the Nginx image from the local system.

docker pull nginx => Downloads the Nginx image from Docker Hub.

docker run ubuntu sleep 5 => Runs a container using the Ubuntu image and executes the sleep 5 command, pausing for 5 seconds before exiting.


<!-- docker run ubuntu
docker ps
    sees nothing
docker ps -a -->

docker run centos
docker run -it centos bash
cat /etc/*release*
ls
exit

docker run -d centos sleep 20
docker ps
docker ps -a
docker rm "container-name" => instead of name i can use the 1st 3 letters of the container id
dokcer rm "873 872 998" => will remove 3 container having the 1st 3 container id with this

docker rm putjar => Removes (deletes) a stopped container named putjar
docker rmi busybus => Removes (deletes) a Docker image named busybus from your system.

While removing a image 1st we have to remove the container then the image .

docker pull ubuntu

docker run -d ubuntu sleep 100 => Runs an Ubuntu container in detached mode (-d) that executes the sleep 100 command, keeping it alive for 100 seconds.

docker exec cla19d3a7ca7 cat /etc/*release* => It runs the cat /etc/*release* command inside the running container with ID cla19d3a7ca7, to display the 
    Linux distribution information (like Ubuntu, Debian, etc.).