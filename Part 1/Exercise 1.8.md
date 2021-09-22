## Dockerfile
```
FROM ubuntu:18.04
COPY website.sh .
RUN apt update && apt install curl -y
CMD ./website.sh
```
## file "website.sh"

```
#!/bin/sh

echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;
```

## Result

![image](https://user-images.githubusercontent.com/75350516/134366042-b2b1876b-4231-4600-a026-f5854aae25e8.png)
