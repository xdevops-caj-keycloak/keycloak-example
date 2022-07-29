# Keycloak Getting Started

## Access Keycloak admin console

Access Kecloak admin console with `admin/admin`:
- http://localhost:8080/admin


## Create a realm
Create a realm (tenant，租户)
- `myrealm`

## Create a user
Create a unser under `myrealm`
- Username: `john`
- First name: `John`
- Laste name: `Dae`

Set user password:
1. Open Credentials, click "Set password"
2. Fill in and confirm password
3. Click ON for temporary (need reset password when user first login)

The default password encrypt algorithm is `pbkdf2-sha256`

## Login to account console
Access Keycloak account console with previous created user:
http://localhost:8080/realms/myrealm/account

You need reset password if checked temporary password when set initial password.

## Secure your first app

### Create a client

Under `myrealm` realm, open Clients, create a client:
- Client type: `OpenID Connect` 
- Client ID: `myclient`

Configure client:
- Root URL: `https://www.keycloak.org/app/`
- Valid redirect URIs:
    - `https://www.keycloak.org/app/*` (dont forget `*`)

Save configuration.

Open https://www.keycloak.org/app/ and click Save to use the default configuration.
It will direct to below link:
- https://www.keycloak.org/app/#url=http://localhost:8080&realm=myrealm&client=myclient

Now you can click Sign in to authenticate to this application using the Keycloak server you started earlier.

## References
- https://www.keycloak.org/getting-started/getting-started-podman