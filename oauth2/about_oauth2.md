# About OAuth2

OIDC 负责认证(authentication)，OAuth2 负责授权（authorization）。

## OAuth2 Roles

There are four roles defined in OAuth 2.0:
- **Resource owner**: This is typically the end user that owns the resources an application wants to access.
- **Resource server**: This is the service hosting the protected resources.
- **Client**: This is the application that would like to access the resource.
- **Authorization server**: This is the server issuing access to the client, which is the role
of Keycloak.


In essence, in an OAuth 2.0 protocol flow:
1. The client requests access to a resource on behalf of a resource owner from the authorization server.
2. The authorization server issues a limited access to the resource in the form of an access token. 
3. After receiving the access token, the client can access the resource at the resource server by including the access token in the request.

基于**access token**的授权方式。

## OAuth2 Authorization Flow

- 一般使用Authorization Code flow
- 如果应用访问自己的资源，用Client Credentials flow
- 如何是设备访问资源（不方便输入用户名和密码），用Device flow
- 因为安全原因，不应该使用以下方式：
    - Implicit flow
    - Resource Owner Password Credentials flow (为什么Keycloak默认勾选"Direct access grants"??)


## OAuth2 Authorizaiton Code flow

1. 用户被重定向到Keycloak登录页面
1. 用户登录（身份认证）成功后，获取Authorization Code
2. 用Authorization Code换取Access Token
3. 带着Access Token访问受保护的服务

Keycloak endpoints:
- 登录页面
- authentication endpoint (提交登录信息后，进行身份认证)
- authorization endpoint (获取authroization code)
- token endpoint (用Authorization Codeh换取Access Token)
- refresh endpoint （刷新access token）

不能泄漏的东西：
- 用户名/密码
- authroization code
- access token
- refresh token
- client secret

## OAuth2 Client types

- confidential client: 可以安全保存client credential的服务端应用程序
- public client: 无法安全保存client credential的客户端应用程序（浏览器，手机App）

公共客⼾端⽆法通过授权服务器进行⾝份验证，配套的保护机制：
- 授权服务器只将authroization code发给指定的url（就是keycloak中配置的valid redirect uri)
- **Proof Key for Code Exchange (PKCE, RFC 7636)**, which is an extension to OAuth 2.0, prevents anyone that intercepts an authorization code from exchanging it for an
access token.

小结：
防止其他来源的人获取authroization code，万一authroization code被窃取，防止拿着authroization code来换取access token

## OAuth2 Tokens

- Token类型为Bearer Tokens (RFC 6750)
    - 一般通过HTTP Authorization header来存放该token
- 令牌自省，Token Introspection (RFC 7662)
    - 获取令牌信息，校验令牌的完整性（防止令牌被篡改）
- 令牌撤销，Token Revocation (RFC 7009)
    - 撤销已颁发的access token

Token有有效期，可以通过keycloak的refresh endpoint刷新（获取新的）access token。





