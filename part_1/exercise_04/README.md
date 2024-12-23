# EXERCISE 1.4: MISSING DEPENDENCIES

Start a Ubuntu image with this process:
	`sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done'`

Few things required for proper execution are missing. Be sure to remind yourself which flags to use so that the container actually waits for input.

curl is NOT installed in the container yet. You will have to install it from inside of the container.

Test inputting `helsinki.fi` into the application.

This time return the command you used to start process and the command(s) you used to fix the ensuing problems.

Hint: for installing you can use `docker exec`.

# Solution

## 1. Start the image, update, install, start the process

```bash
sudo docker run --rm -it --name website ubuntu sh -c 'apt update && apt upgrade && apt install -y curl; while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done '
```


