# EXRCISE 1.1: GETTING STARTED

Start 3 containers from an image that does not automatically exit (such as nginx) in detached mode.

Stop two of the containers and leave one container running.

Submit the output for `docker ps -a` which shows 2 stopped containers and one running.

# Solution

## 1. Start 3 containers from an image (in detached mode)

```bash
docker run -d nginx
docker run -d nginx
docker run -d nginx
```

## 2. Stop 2 containers (doesn't matter which one)

```bash
sudo docker stop 41600f2f1804
sudo docker stop bf389a2d4713
```

## 3. show output for `docker ps -a` command

CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                     PORTS     NAMES
41600f2f1804   nginx     "/docker-entrypoint.…"   7 minutes ago   Exited (0) 7 minutes ago             dazzling_albattani
bf389a2d4713   nginx     "/docker-entrypoint.…"   7 minutes ago   Exited (0) 7 minutes ago             objective_wozniak
09c3b0c3f104   nginx     "/docker-entrypoint.…"   7 minutes ago   Up 7 minutes               80/tcp    bold_kare
