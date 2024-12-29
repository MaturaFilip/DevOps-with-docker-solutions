# EXERCISE 1.10 PORTS OPEN

The image `devopsdockeruh/simple-web-service` will start a web service in port `8080` when given the argument "server". In Exercise 1.8 you already did an image that can be used to run the web service without any argument.

Use now the -p flag to access the contents with your browser. The output to your browser should be something like: `{ message: "You connected to the following path: ...`

Submit your used commands for this exercise.

# Solution

## 1. Map the host port 80 to container 8080

```bash
sudo docker run --rm -p 80:8080 devopsdockeruh/simple-web-service server
```
