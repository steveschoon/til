# Terminal into Conatiner

To show names of all running containers:

```
docker container ls
```

To open a terminal in a running container:

```
docker exec -it CONTAINER_NAME_OR_ID /bin/bash
```
