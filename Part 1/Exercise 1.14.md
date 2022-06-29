## Dockerfile "Example-frontend"

```
FROM ubuntu:20.04

WORKDIR /app

EXPOSE 5000

RUN apt update && apt install curl -y
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash && apt install -y nodejs

COPY . .

RUN npm install build && REACT_APP_BACKEND_URL=http://localhost:8080 npm run build

RUN npm install -g serve

CMD ["serve", "-s", "-l", "5000", "build"]

```

## Dockerfile "Example-backend"

```
FROM ubuntu:20.04

EXPOSE 8080

WORKDIR /app

COPY . .

RUN apt update && apt install -y wget gcc && \
    wget https://go.dev/dl/go1.18.3.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.3.linux-amd64.tar.gz

ENV PATH=$PATH:/usr/local/go/bin

ENV REQUEST_ORIGIN http://10.20.20.30:5000

RUN go build

CMD ./server

```

## Result 

![image](https://user-images.githubusercontent.com/75350516/176378055-60587ca4-8dcd-45d0-8c20-0e4a2c3973b0.png)

