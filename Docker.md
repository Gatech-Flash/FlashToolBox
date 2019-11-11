# Docker

[Introduction from docker.com](https://docs.docker.com/get-started/)

```bash
docker run -it --rm \
-v ~/project/MNLI:/work/MNLI \
-v ~/.ssh:/root/.ssh \
-v /mnt:/work/data \
--privileged mnli bash

# on lambda
docker run --runtime=nvidia -it --rm -v ~/Desktop/:/work/project -v ~/.ssh:/root/.ssh -v ~/Desktop/data/:/work/data --privileged mnli bash

docker run -it --rm  -v ~/project:/work/project biglm bash
docker run -it --rm  -v ~/project:/work/project fairseq bash
docker run -it --rm -v ~/project/MNLI:/work/MNLI --privileged tscience.azurecr.io/biglm/biglm:1.12-0.4.1-cuda9.2-py36 bash
```

## Run a docker image

```bash
docker run -it --rm  -v /local_dir:/docker_dir docker-image:tag bash
```
`-it`: interactive mode
`--rm`: clean up after exit
`-v`: volume (shared filesystems)

## Attach to a running docker container
```bash
docker ps
docker exec -it container_name bash
```

## File Permission Issue
All files created by the docker is owned by root.
Solution: [Using ACL](https://www.berthon.eu/2018/containers-volumes-and-file-permissions/)
The following command grant use ACL to make read/write permissions of all files in `project` inherit from project and have the same access of the current host user.
```bash
setfacl -dm "u:username:rwx" ~/project
```

## SSH in docker
Add this line to use the ssh key as the host
```bash
-v ~/.ssh:/root/.ssh
```


## Build a docker image
1. Get folder with everything you need in it.
2. Write a `Dockerfile`
3. `docker build --tag=docker-image .`

## Cheatsheet
```bash
## List Docker CLI commands
docker
docker container --help

## Display Docker version and info
docker --version
docker version
docker info

## Execute Docker image
docker run hello-world

## List Docker images
docker image ls

## List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -aq
```
