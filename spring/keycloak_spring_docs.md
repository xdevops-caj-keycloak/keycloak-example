# Keycloak and Spring integration docs

## Keycloak docs
- [Securing Applications and Services Guide](https://www.keycloak.org/docs/latest/securing_apps/)

## Spring docs
- [Spring Security OAuth2 Client](https://docs.spring.io/spring-boot/docs/current-SNAPSHOT/reference/htmlsingle/#web.security.oauth2.client)

## Terminology
Terminology:
- Clients
- Applications
- Client adapters
- Creating a client / Registering a client
- A service account

## Spring Support
OIDC:
- [Spring Boot](https://www.keycloak.org/docs/latest/securing_apps/#_spring_boot_adapter)
- [Spring Security](https://www.keycloak.org/docs/latest/securing_apps/#_spring_security_adapter)

## Basic Steps

1. Configure a client using one of these options:
    - A Keycloak adapter (prefered, Spring Boot adatper or Spring Security adapter)
    - A generic OpenID connect or SAML library
2. Register a client using one of these options:
    - The Keycloak Admin Console (prefered)
    - The client registration service
    - The CLI