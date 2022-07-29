# Install Keycloak via container

> Only use in development environment

## Start Keycloak container without persistent data
```bash
podman run -p 8080:8080 \
  -e KEYCLOAK_ADMIN=admin \
  -e KEYCLOAK_ADMIN_PASSWORD=admin \
  quay.io/keycloak/keycloak:19.0.0 \
  start-dev
```

Access Kecloak admin console with `admin/admin`:
- http://localhost:8080/admin

## Start Keycloak container without persistent data

```bash
# create volume
podman volume create keycloak_vol
pdoman volume ls

# run container with volume
podman run -p 8080:8080 \
  -v keycloak_vol:/opt/keycloak:Z \
  -e KEYCLOAK_ADMIN=admin \
  -e KEYCLOAK_ADMIN_PASSWORD=admin \
  quay.io/keycloak/keycloak:19.0.0 \
  start-dev
```

## References
- https://www.keycloak.org/getting-started/getting-started-podman
- https://www.keycloak.org/server/containers
