# Docker CheatSheet

## Concepts
- Docker is not a virtual machine/sandbox environment.
- Docker is run above operating system, VMs are run above hypervisor.
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
docker ps               # List containers
docker rm `image_id`    # Remove one or more containers
```