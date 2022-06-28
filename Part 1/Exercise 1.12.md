## Dockerfile


```

FROM ubuntu:20.04

WORKDIR /app

EXPOSE 5000

RUN apt update && apt install curl -y
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash && apt install -y nodejs

COPY . .

RUN npm install build && npm run build

RUN npm install -g serve

CMD ["serve", "-s", "-l", "5000", "build"]


```


![image](https://user-images.githubusercontent.com/75350516/176157876-77b6addd-ec06-40a3-a0c7-790d3dc0b95e.png)
