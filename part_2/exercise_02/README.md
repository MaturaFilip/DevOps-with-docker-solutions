EXERCISE 2.2

Read about how to add the command to docker-compose.yml from the documentation.

The familiar image devopsdockeruh/simple-web-service can be used to start a web service, see the exercise 1.10.

Create a docker-compose.yml, and use it to start the service so that you can use it with your browser.

Submit the docker-compose.yml, and make sure that it works simply by running docker compose up

# Solution

# 1. docker-compose.yml

```yml
version: '27'

services:
    simple-web-service:
        image: devopsdockeruh/simple-web-service
        ports:
            - 8080:8080
        command: bash -c "server"
        container_name: simple

```

# 2. run

```bash
docker compose up
```
