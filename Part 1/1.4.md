## Commands:

`docker run -d -it --name web ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'`

`docker exec -it web bash`

`apt update && apt install curl -y `

`docker attach web`

## Result

![image](https://user-images.githubusercontent.com/75350516/134195725-4c794dc4-4832-4b22-baed-02bb6043a9fe.png)
