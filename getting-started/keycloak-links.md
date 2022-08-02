# Keycloak links

Admin console:
- http://localhost:8080/admin

> Replace `http://localhost:8080` as your keycloak root url

Account console:
- http://localhost:8080/realms/myrealm/account

> Repalce `myrealm` as your realm name


Keycloak endpoints:
- http://localhost:8080/realms/myrealm/.well-known/openid-configuration
在Realm settings中，打开OpenID Endpoint Configuration.

Common Endpoints:
- "authorization_endpoint": 
    - 登录后获取authorization code: `response_type=code&scope=openid`
    - "http://localhost:8080/realms/myrealm/protocol/openid-connect/auth"
- "token_endpoint":
    - 根据authorization code获取access token: `grant_type: authorization_code`
    - 刷新Token：`grant_type: refresh_token`
    - "http://localhost:8080/realms/myrealm/protocol/openid-connect/token"
- "introspection_endpoint":
    - 令牌自省，获取Token信息
    - "http://localhost:8080/realms/myrealm/protocol/openid-connect/token/introspect"
- "userinfo_endpoint": 
    - 获取用户信息
    - "http://localhost:8080/realms/myrealm/protocol/openid-connect/userinfo"
- "end_session_endpoint": 
    - Logout
    - "http://localhost:8080/realms/myrealm/protocol/openid-connect/logout"