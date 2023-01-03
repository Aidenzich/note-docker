# Commmands
## Run a command in a new container
```
docker run -d -p <port-host>:<port-container> <repo-name>
```
<details>
  <summary><strong><em>Options</em></strong></summary>

  | Option | Description |
  |-|-|
  | `-d` | run the container in detached mode in the background |
  | `-p <port-host>:<port-containe>` | map the port of the host to the port of the container |
  | `-v` | option to map a host directory to container |
  | | `./` is not available for this option, you have to use `$PWD` instead. e.g. `-v $PWD/.deploy:/data/.deploy` |
</details>

## Build an image from a Dockerfile
```
docker build [OPTIONS] PATH | URL | -
```
`--tty`, `-t`
  - Allocate a pseudo-TTY

## List containers
```
docker ps 
docker container ls
```
<details>
  <summary><strong><em>Options</em></strong></summary>

  | Option | Description |
  |-|-|
  | `-a` `--all` | Show all containers (default shows just running) |
  | `-f` `--filter` | Filter output based on conditions provided  |
  | `-s` `--size` | Display total file sizes |
  | `-n` `--last` | Show `n` last created containers |
  | `-q` `--quiet` | Only display container IDs |
</details>

## Check container output messages
```sh
docker logs <container-id>
```

<details>
  <summary><strong><em>Options</em></strong></summary>

  | Option | Description |
  |-|-|
  | `-f` `--follow` | following log messages |
</details>


## Get container local ip
```sh
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container-id>
```


## Save image to `.tar` file
```sh
docker save you-image-name > <your-file>.tar
```


## Stop & Clear
| Operation | commands |
|-|-|
| stop all processes | `docker stop $(docker ps -aq)` |
| stop specific processes | `docker stop <container-id>` |
| remove all containers | `docker rm $(docker ps -aq)` |
| remove all images | `docker rmi $(docker images -aq)` |
| delete all volumes | `docker volume prune` |
| delete specific images | `docker rmi <your-image-id> <your-image-id> ...` |

## Endpoint vs Command
- [Great Disscussion](https://stackoverflow.com/questions/21553353/what-is-the-difference-between-cmd-and-entrypoint-in-a-dockerfile)