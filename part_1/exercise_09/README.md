# EXERCISE 1.9: VOLUMES

Image `devopsdockeruh/simple-web-service` creates a timestamp every two seconds to `/usr/src/app/text.log` when it's not given a command. Start the container with a bind mount so that the logs are created into your filesystem.

Submit the command you used to complete the exercise.

# Solution

## 1. Create and start container with a bind mount

```bash

# if we didn't create file it will automatically creates a directory
touch text.log

sudo docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```
