# EXERCISE 1.3: SECRET MESSAGE

Get inside a container while it's running!

Image `devopsdockeruh/simple-web-service:ubuntu` will start a container that outputs logs into a file. Go inside the running container and use `tail -f ./text.log` to follow the logs. Every 10 seconds the clock will send you a "secret message".

Submit the secret message and command(s) given as your answer.

# Solution

## 1. Run the container 

```bash
sudo docker run -d --name secret_message --rm -it devopsdockeruh/simple-web-service:ubuntu
```

## 2. Attach the container 

```bash
sudo docker exec -it secret_message bash
```

## 3. Read the secret message and show it

```bash
tail -f ./text.log
```
Secret message is: 'You can find the source code here: https://github.com/docker-hy'

