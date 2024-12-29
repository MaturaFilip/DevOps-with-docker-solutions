# EXERCISE 1.11: SPRING

Create a Dockerfile for an old Java Spring project that can be found from the course repository: https://github.com/docker-hy/material-applications/tree/main/spring-example-project

The setup should be straightforward with the README instructions. Tips to get you started:

There are many options for running Java, you may use eg. amazoncorretto FROM amazoncorretto:_tag_ to get Java instead of installing it manually. Pick the tag by using the README and Docker Hub page.

You've completed the exercise when you see a 'Success' message in your browser.

Submit the Dockerfile you used to run the container.

## 1. Clone the repository and go to correct dir

```bash
git clone https://github.com/docker-hy/material-applications/tree/main

cd material-application/spring-example-project
```

## 2. Create Dockerfile

`
FROM amazoncorretto:latest


WORKDIR /usr/app

EXPOSE 8080

COPY . .


RUN ./mvnw package

CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
`

## 3. Build the conteiner

```bash
sudo docker build -t spring .
```

## 4. Run the conteiner

```bash
sudo docker run --rm -p 8080:8080 spring
```
