# Docker Traefik container

## Installation

1. Create htpasswd/traefik file for Traefik dashboard Basic Auth

```shell
htpasswd -bc traefik/htpasswd/traefik your_user your_password
```

## Usage

Open dashboard domain from variable TRAEFIK_HOST, example `traefik.localhost`
