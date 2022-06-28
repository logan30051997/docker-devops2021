## Dockerfile

```
FROM ubuntu:20.04

EXPOSE 8080

WORKDIR /app

COPY . .

RUN apt update && apt install -y wget gcc && \
    wget https://go.dev/dl/go1.18.3.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.3.linux-amd64.tar.gz
ENV PATH=$PATH:/usr/local/go/bin

RUN go build

CMD ./server
```

## Command

`sudo docker run -d -p 8080:8080 test`




![image](https://user-images.githubusercontent.com/75350516/176168093-cacc8f88-80ac-4c76-b2ea-7d7374be025a.png)
