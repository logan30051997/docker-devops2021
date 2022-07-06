## docker-compose.yml

```
services:
        redis:
                image: redis
                ports:
                        - 6379:6379
                container_name: redis
        frontend:
                image: example-frontend
                ports: 
                - 5000:5000
                container_name: frontend 

        backend:
                image: example-backend
                ports:
                        - 8080:8080
                container_name: backend
                environment:
                        REDIS_HOST: localhost
                        
```

## Result

![image](https://user-images.githubusercontent.com/75350516/177491032-c88924f4-58a2-46af-be1f-32c4859aabc2.png)
