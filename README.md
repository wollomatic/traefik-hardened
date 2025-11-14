# traefik2-hardened

This is an example configuration of Traefik v2 for use with docker compose.
It demonstrates some good security practices like running as an unprivileged user, using a read-only container and not mounting the docker socket into the container.

As of October 2023, the Tecnativa docker socket proxy is replaced with wollomatic/socket-proxy.
This is because the new socket proxy is written in Go, allowing a more hardened deployment. For an example with Technativa's docker proxy, see the the docker-compose.yaml file tagged before 2.10.

TLS certificates are generated automatically using Let's Encrypt.

> [!IMPORTANT]
>## Usage with Traefik => 2.11.31 / => 3.6.1
>Due to a change in how Traefik retrieves the Docker API version (traefik/traefik#12256), the Socket-Proxy configuration for Traefik must be updated to allow `HEAD` requests to `/_ping`:
>
>      - '-allowHEAD=/_ping'
>
>Otherwise, Traefik would fall back to API version 1.51, which would break the Docker provider on older Docker versions.


Otherwise, Traefik would fall back to API version 1.51, which would break the Docker provider on older Docker versions.
