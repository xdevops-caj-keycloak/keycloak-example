# Install Keycloak via OpenJDK

```bash
bin/kc.sh start-dev
````

Keycloak does not come with a default admin user, which means before you can start using Keycloak you need to create an admin user.

To do this open http://localhost:8080/, then fill in the form with your preferred username and password.


## References
- https://www.keycloak.org/getting-started/getting-started-zip
- https://www.keycloak.org/server/configuration
- https://www.keycloak.org/docs/latest/server_installation/index.html#guide-overview