Docker
======

### docker kill
```bash
    docker_kill() {
        sudo docker kill $(docker ps -q)
        sudo docker rm $(docker ps -a -q)
    }
```

### docker rmi <none> image
```bash
    sudo docker rmi $(docker images | grep "^<none>" | awk "{print $3}")
```
