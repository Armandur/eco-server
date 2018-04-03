# Eco Game Server Docker Image

## How to use

```
mkdir -p ~/eco-server/Storage ~/eco-server/Configs

docker run -d --name "eco-server" -v ~/eco-server/Storage:/srv/eco-server/Storage -v ~/eco-server/Configs:/srv/eco-server/Configs --network=host armandur/eco-server:latest
```

## How to build

```
make build
```

## Example docker-compose.yml

```
eco-server:
  image: armandur/eco-server:latest
  ports:
  - 2999:2999/udp
  - 3000:3000
  - 3001:3001
  volumes:
  - ./Storage:/srv/eco-server/Storage:rw
  - ./Configs:/srv/eco-server/Configs:rw
  privileged: true
```
