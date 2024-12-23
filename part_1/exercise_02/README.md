# EXERCISE 1.2: CLEANUP

Run `docker ps -a` and `docker image ls` to confirm that we have some exited containers and image no longer in use

Clean the Docker daemon by removing all images and containers

Submit the output for `docker ps -a` and `docker image ls`

# Solution

## 1. run commands to check images and containers

```bash
sudo docker ps -a
sudo docker image ls
```

## 2. remove all images and containers (you need to stop some containers)

```bash
sudo docker stop 09c3b0c3f104
sudo docker system prune -a
```

## 3.1 show all containers

CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

## 3.2 show all images

REPOSITORY   TAG       IMAGE ID   CREATED   SIZE



