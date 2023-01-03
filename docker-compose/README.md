# Docker Setting Document
## Cheat sheet
| Operate | Command |
|-|-|
| Run containers and aggregates the output of each container | `docker-compose up` |
| Run containers in the background | `docker-compose up -d` |
| Build images before starting containers. | `docker-compose up --build` |
| Stops containers and removes containers, networks, volumes, and images created by up | `docker-compose down` |
| List images used by the created containers | `docker-compose images` |

## Details of `docker-compose.yaml`
### Tags
| tag-name | desp |
|-|-|
| `version` | The version of docker-compose, different versions support different degrees. |
| ~~`links`~~ | ~~Links allow you to define extra aliases by which a service is reachable from another service.~~(have been replaced by `networks`) |
| `environment` | Add environment variables. `-e` |

- Check cheat sheet [here](https://devhints.io/docker-compose)

## Commands
### `docker-compose up`
<details>
  <summary><strong><em>Options</em></strong></summary>

  | Option | Description |
  |-|-|
  | `--detach` , `-d` | Run the container in detached mode in the background |
  | `--build` | Build images before starting containers. |
  | `--no-build` | Don't build an image, even if it's missing. |
  | `--force-recreate` | Recreate containers even if their configuration and image haven't changed. |
</details>


