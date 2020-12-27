# Docker

## Helpful Docker Commands
Below are some less-common Docker commands you might find useful.

### Get Runtime Statistics
``` bash
docker stats $(docker ps --format='{{.Names}}')
```

This command will display detailed information about the docker containers you have running locally including:

* Container Name
* Name
* CPU %
* Memory Usage/Limit Memory %
* Network I/O
* Block Storage I/O
* Process IDs 

### Remove All Stopped Containers

```bash
docker rm $(docker ps -a -q)
```

If you have a lot of stopped containers (perhaps you didn't supply a container name when running images), you can run this command to automatically remove all stopped containers.

### Remove Untagged Containers

``` bash
docker images -q --filter "dangling=true" | xargs docker rmi
```

### Prune Everything
```bash
docker system prune --volumes
```

This command will remove all unused:

* Containers
* Images (dangling & unused)
* Networks
* (Optionally) Volumes

!!! note
    If you do not want to prune volumes, remove `--volumes` from the command above.