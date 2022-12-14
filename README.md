# Docker containers collection

## Requirements

- GIT
- [Docker v19.03.0+](https://docs.docker.com/get-docker/)
- Docker Compose specification v3.8

## Installation

1. Clone repo with command:

```shell
git clone https://github.com/ast21/docker-collection.git
```

2. Create `.env` file and set environments
```shell
cp .env.example .env
```

3. Create docker networks
```shell
docker network create proxy
docker network create databases
docker network create tools
```

## Usage

### Options

Use one of these options

#### 1. Use `COMPOSE_PROFILES` env on default

For current terminal session you need to set `COMPOSE_PROFILES` env, for example:
```shell
export COMPOSE_PROFILES=proxy
```

or with multiple profiles 
```shell
export COMPOSE_PROFILES=proxy,adminer
```

After use `docker compose` is only for exported profiles for your current terminal session
```shell
docker compose up -d
```

#### 2. Use `COMPOSE_PROFILES` env for current command

```shell
COMPOSE_PROFILES=proxy docker compose up -d
```

or with multiple profiles
```shell
COMPOSE_PROFILES=proxy,adminer docker compose up -d
```


#### 3. Use `--profile` flag for docker command

```shell
docker compose --profile=proxy --profile=adminer up -d
```

### Overriding compose file

Create file `docker-compose.override.yaml`. See the example:
```yaml
# docker-compose.override.yaml

services:
  postgresql:
    ports: [ "5432:5432" ]
```

Then run your any command.

## License
[MIT](https://choosealicense.com/licenses/mit/)