EXERCISE: 1.7: IMAGE FOR SCRIPT

We can improve our previous solutions now that we know how to create and build a Dockerfile

Let us now get back to Exercise 1.4

Create a new file script.sh on your local machine with the following contents:

```bash
while true
do
	echo "Input website:"
	read website; echo "Searching.."
	sleep 1; curl http://$website
done
```

Create a Dockerfile - ubuntu:22.04, add instructions to install `curl`, copy the script file into that image, run the script with CMD (don't forgot permission to run the script)

Then build the image with the name "curler"

Submit the Dockerfile

# Solution

## 1. Create script.sh with the content shown above

```bash
vim script.sh
```

## 2. Create and show the Dockerfile

`
  1 FROM ubuntu:22.04
  2 
  3 RUN apt update && apt upgrade
  4 RUN apt install curl -y
  5 
  6 WORKDIR /usr/src/app
  7 
  8 COPY script.sh .
  9 
 10 RUN chmod +x script.sh
 11 
 12 CMD ./script.sh
`

## 3. build image with the name "curler".

```bash
docker build . -t "curler"
```

## 4. run it 

```bash
sudo docker run -it curler
```
