# Caddy reverse proxy server

Standard Caddy web server deployed with docker compose.

## !!! Important !!!
As caddy is going to work as a reverse proxy with another docker compose stacks, 
you need to create an external docker network first.
After that, use the name of the network to connect to other docker stacks.

### !!! Important !!!
Remember to remove port mapping from all docker compose files,
as Caddy is going to handle them automatically.

### Create external docker network for all docker compose stacks
```commandline
docker network create caddy-proxy-network
```

### Reloading caddy configuration
```commandline
docker compose exec -w /etc/caddy caddy caddy reload.
```