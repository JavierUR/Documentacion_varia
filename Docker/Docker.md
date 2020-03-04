# Docker

## Install on ubuntu

```bash
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository \
  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) \
  stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce
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



## Delete non tagged images

```bash
docker rmi $(docker images | grep "^<none>" | awk "{print $3}")
```

