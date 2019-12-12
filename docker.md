# Docker CheatSheet

## Concepts
- **Docker is not a virtual machine/sandbox environment**.
- Docker is run above operating system (docker daemon runs and communicates with the os using commands via docker.sock); whereas VMs are run above hypervisor.
![](https://i.imgur.com/PxdN0Wo.png)

- Relatively similar concepts

| Docker | VM |
| --- | --- |
| Docker | Hypervisor |
| Images | .iso file |
| Container | Virtual Machine |

## Install
```bash
# Install docker
:~$ curl -fsSL https://get.docker.com -o get-docker.sh
:~$ sudo sh get-docker.sh
# Allow non-root sudo user to run docker (Needs to reboot)
:~$ sudo usermod -aG docker $USER
```

## Login
```bash
docker login -u `username`
```

## Docker Images
```bash
docker images   # List images
docker rmi      # Remove one or more images
docker pull `username`/`image`  # Pull docker image from docker hub
docker push `username`/`image`  # Push docker image to docker hub
```

## Docker Containers
```bash
docker ps                       # List running containers (add `-a` for all)
docker stop `container_id`      # Stop one or more container(s)
docker stop $(docker ps -a -q)  # Stop all containers
docker rm `container_id`        # Remove one or more container(s)
docker rm $(docker ps -a -f status=exited -q) # Remove all exited containers
```

## Docker Run
```bash
docker run [options] `username`/`image`[:tag] [command]
```

- options
    - `-d` - Detached mode (default: false)
    - `--name` - Define a name for container identification (default: random str)

- `:TAG` - Specifies a particular version of the image

## TODO: Dockerfile