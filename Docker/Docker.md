# Docker

## Install on ubuntu

```
sudo apt-get install docker.io
```

### (optional) add user to docker group

Necessary to  execute docker commands without sudo

```
sudo usermod -a -G docker $(whoami)
```



## Get used space by images and containers

```bash
docker system df --verbose
```



## Get list of all containers

```bash
docker container ls -a
```



## Delete stopped containers

```bash
docker container prune
```

## Delete specific container

```bash
docker container rm <name_or_id>
```

