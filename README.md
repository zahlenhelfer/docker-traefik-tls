# how to use traefik as a Let´s-Encrypt Proxy with `docker-compose`

We setup a docker-compose that mimic the following behaivor

```mermaid
flowchart TD
    A["Internet"] -- :443 --> B["Traefik"]
    B -- :8080 --> C["Frontend"] & D["API"]
```

- User will connect to Traffic via `TLS:443``
- Traefik do all the plumping for TLS with LetsEncrypt
- Traefik forward the request via Rules to the appropiate docker-containers (`frontend` or `api`)

Before you can start - choose your flavor

## `subdomain.domain.com`

### `anything.subdomain.domain.com`
