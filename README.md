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

Run container:
```shell
docker compose up -d postgresql
```

or run with multiple containers:
```shell
docker compose up -d postgresql adminer
```



### Overriding compose file

Create file `docker-compose.override.yaml`.
```shell
cp docker-compose.override.yaml.example docker-compose.override.yaml
```

See the example:
```yaml
# docker-compose.override.yaml

services:
  postgresql:
    ports: [ "5432:5432" ]
```

Then run your container.

## License
[MIT](https://choosealicense.com/licenses/mit/)