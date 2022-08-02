# About JWT

## JWT家族
JWT comes from a family of specifications known as JOSE, which stands for JavaScript Object Signing and Encryption. The related specifications are as follows:
- JSON Web Token (JWT, RFC 7519): Consists of two base64url-encoded JSON
documents separated by a dot, a header, and a set of claims
- JSON Web Signature (JWS, RFC 7515): Adds a digital signature of the header and the claims
- JSON Web Encryption (JWE, RFC 7516): Encrypts the claims
- JSON Web Algorithms (JWA, RFC 7518): Defines the cryptographic algorithms
that should be leveraged for JWS and JWE
- JSON Web Key (JWK, RFC 7517): Defines a format to represent cryptographicmkeys in JSON format

In addition to the preceding specifications, the OpenID Connect Discovery endpoint
advertises an endpoint where the JSON Web Key Set (JWKS) can be retrieved, as well
as what signing and encryption mechanisms from the JWA specification are supported.

When a resource server receives an access token, it is able to verify the token in the following ways:
- Retrieving the JWKS URL from the OpenID Connect Discovery endpoint.
- Downloading the public signing keys for the OpenID Provider from the JWKS URL endpoint. These are typically cached/stored at the Resource Server.
- Verifying the signature of the token using the public signing keys from the OpenID Provider.

use an OpenID Connect/OAuth 2.0 library that supports
JWT as the access token

