# EXERCISE 1.5: SIZES OF IMAGES

Use Alpine Linux with app: `devopsdockeruh/simple-web-service:alpine` and ubuntu

Pull both images and compare the sizes: Go inside the Alpine container and make sure the secret message functionality is the same. Alpine version doesn't have bash but it has sh, a more bare-bones shell.

# Solution

## 1. Run the ubuntu from exercise 1.3

```bash
sudo docker run devopsdockeruh/simple-web-service:ubuntu
```

## 2. Run the Alpine linux

```bash
sudo docker run devopsdockeruh/simple-web-service:alpine

```bash
sudo docker exec -it clever_wilbur sh
```

## 3. Images size
Alpine linux image: 15.7MB
Ubuntu linux image: 83MB


## 4. Go inside the Alpine container. Does it have same functionality like ubuntu in 1.3?

No, it print secret message every 6 line
