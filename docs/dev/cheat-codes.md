# Cheat Codes

![Cheat Codes](/assets/img/cheat-code.png)

The [Konami Code][2]
{: .caption }

## Docker
Below are some less-common Docker commands.

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

### Troubleshooting

#### Cannot Connect to Container from Host

In order to connect to a webserver you have running on your docker container, make sure you bind the server to `0.0.0.0` and **not** `127.0.0.1` like you would locally.

## Git

### Remove Items from Git w/o Deleting
If you ever accidentally added something to your git repository and want to remove it from git without actually deleting the local version, you can run one of these commands:

```bash
git rm --cached <file-name>
```

Remove a **file** from git without deleting it locally
{: .caption }

```bash
git rm --cached -r <directory-name>
```

Remove an entire **directory** from git without deleting it locally
{: .caption }

### Repoint Remote Endpoint

```bash
git remote set-url <remote-name> <url>
```

If you ever move your code to a new [remote system][1] (say from GitHub to GitLab), you can use this command to re-point your remote without having to remove and add the remote from scratch.

## Python

### Lock pip Dependencies

```bash
pip freeze > requirements.txt
```

### Run as a Module

```bash
pip install -e .
```

[1]: https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes
[2]: https://www.howtogeek.com/659611/what-is-the-konami-code-and-how-do-you-use-it/