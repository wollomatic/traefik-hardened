# traefik2-hardened

This is an example configuration of Traefik v2 for use with docker compose.
It demonstrates some good security practises like running as an unprivileged user, using a readonly container and not mounting the docker socket into the container.

TLS certificates are generated automatically using Let's Encrypt.
