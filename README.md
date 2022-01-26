# traefik2-hardened

This is an example configuration of Traefik v2 for use with docker compose.
It demonstrates some good security practises like running as an unprivileged user, using a readonly container and not mounting the docker socket into the container.

TLS certificates are generated automatically using Let's Encrypt.

## Let's Encrypt TLS-ALPN-01 issue
Due to some changes to TLS-ALPN-01 challenge by Let's Encrypt (see https://community.letsencrypt.org/t/changes-to-tls-alpn-01-challenge-validation/170427) on 2022-01-26, generated certificates will be revoked on 2022-01-28.

Since this sample configuration uses TLS challenge, our created certificates are affected. To solve this issue, you have to delete the certificates in ./config/acme/acme.json
Erase the array in "Certificates" (clear everything between \[ and \] ) or clear the complete file.
After that, traefik has to be restarted.
