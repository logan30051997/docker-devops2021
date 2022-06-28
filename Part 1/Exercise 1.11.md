## Dockerfile
`

FROM openjdk:8

WORKDIR /usr/src/app

EXPOSE 8080

COPY . .

RUN ./mvnw package

CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
`

![image](https://user-images.githubusercontent.com/75350516/176137835-19af77b4-4aa3-4b8f-81e8-77a91aedc37c.png)
