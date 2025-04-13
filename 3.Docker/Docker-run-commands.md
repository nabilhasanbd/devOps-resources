
docker run ubuntu cat /etc/*release*
docker run ubuntu:22.04 cat /etc/*release*
    
    docker run: Runs a new Docker container.
    ubuntu: Uses the official Ubuntu image from Docker Hub.
    cat /etc/*release*: Displays Linux distribution information (like name and version).