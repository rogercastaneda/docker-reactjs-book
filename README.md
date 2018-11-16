# docker-reactjs-book
Basic docker image for the project azat-co/reactjs-quickly


## docker-compose example

```yaml
version: '3'
services:
  reactquickly:
    image: rogercastaneda/reactjs-book
    container_name: reactquickly
    volumes:
      - $PWD/:/app/
    ports:
      - "8080:8080"
    command:
      sh -c  "static -a 0.0.0.0"

  # in case you want to build in live instead of access to the container and run the build command
  reactquickly_build:
    image: rogercastaneda/reactjs-book
    container_name: reactquickly_build
    volumes:
      - $PWD/:/app/
    command:
      sh -c  "npm run build"
```

## bash to container

`$ docker exec -it reactquickly_server sh`