# About OIDC

## OAuth2 vs. OIDC

- OAuth2 (授权鉴权)
    - Access token
    - Invoke resource
- OIDC （身份认证）
    - ID token
    - Establish session

OIDC是对OAuth2的扩展

## Why OIDC

- 实现企业内部Single Sign On（单点登录，统一登录）
- 避免多次输入用户名和密码
- 支持社交登录

## OIDC Roles

- End User：最终用户，resource owner
- Relying Party (RP)：依赖方，依赖于OpenID Provider作身份认证
- OpenID Provider (OP): Keyclok的作用

End User -> Relying Party -> OpenID Provider


OpenID Connect 使⽤ OAuth 2.0 中的授权代码授权类型。主要区别在于客⼾端在初始请求中包含 `scope=openid`，这使其成为 **⾝份验证请求**，⽽不是**授权请求**。


## OIDC Addition

In addition to the OpenID Connect Core specification, there are a few additional
specifications you should be aware of:
- **Discovery**: Allows clients to dynamically discover information about the OpenID
Provider
- **Dynamic Registration**: Allows clients to dynamically register themselves with the
OpenID Provider
- **Session Management**: Defines how to monitor the end user's authentication session
with the OpenID Provider, and how the client can initiate a logout
- **Front-Channel Logout**: Defines a mechanism for **single sign-out** of multiple
applications using embedded iframes
- **Back-Channel Logout**: Defines a mechanism for **single sign-out** for multiple
applications using a back-channel request mechanism, which we will cover in the
next chapter


## JWT

Keycloak使用JWT作为访问令牌的默认格式。

JWT token的信息不是透明的，因此一旦泄漏，会有安全风险。
通过设置JWT token的有效期，来减少JWT token泄漏的风险。

由于资源服务器现在能够直接读取访问令牌的值，因此它们不必总是向 OAuth 2.0 令牌⾃省端点或OpenID Connect UserInfo 端点发出请求。这可能会消除对 Keycloak 的两个额外请求以请求资源服务器，从⽽减少延迟并显着减少对 Keycloak 的请求数量。



