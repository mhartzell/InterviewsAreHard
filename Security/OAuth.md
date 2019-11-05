[<< Back to Security](index.md)

# OAuth

OAuth is an open protocol to allow secure authorization in a simple and standard method from web, mobile and desktop applications.

# Roles

## The User

The user is the “resource owner”.  The resource owner is the person who is giving access to some portion of their account.  Any system that wants to act on behalf of the user must first get permission from them.

## The API

The API is the “resource server”.  The resource server is the server that contains the user’s information that is being accessed by the third-party application. The resource server must be able to accept and validate access tokens and grant the request if the user has allowed it.

## The Authorization Server

The authorization server is what the user interacts with when an application is requesting access to their account. This is the server that displays the OAuth prompt, and where the user approves or denies the access request. The authorization server is also responsible for granting access token after the user authorizes the application.

## The Client

The client is the app that is attempting to act on the user’s behalf or access the user’s resources. Before the client can access the user’s account, it needs to obtain permission.

Confidential clients are clients which have the ability to maintain the confidentiality of the client_secret. Typically these clients are only applications that run on a server under the control of the developer, where the source code is not accessible to users.

Public clients cannot maintain the confidentiality of a client_secret, so the secret is not used for these apps. Both mobile apps and Javascript apps are considered public clients. Since anyone running a Javascript app can easily view the source code of the application, a secret would be visible there trivially.

# Tokens

## Bearer Token

## Access Token

An access token is the string used when making authenticated requests to the API. The token represents that the user has authorized a third-party application to access that user’s account. The token has a corresponding duration of access, scope, and potentially other information.

## Refresh Token

A refresh token is a string that is used to get a new access token when an access token expires. Not all APIs use refresh tokens.

## Authorization Code
An authorization code is an intermediate token that is returned to the client after the authorization step, and then the client exchanges it for an access token.

# Grant Types and Flows

OAuth provides multiple different authorization mechanisms.

## Authorization Code

The authorization code grant is used when an application exchanges an authorization code for an access token. After the user returns to the application via the redirect URL, the application will get the authorization code from the URL and use it to request an access token. This request will be made to the token endpoint.

## Password

The Password grant is used when the application exchanges the user’s username and password for an access token.  A common use for this grant type is to enable password logins for your service’s own apps. Users won’t be surprised to log in to the service’s website or native application using their username and password, but third-party apps should never be allowed to ask the user for their password.

## Client Credentials

The Client Credentials grant is used when applications request an access token to access their own resources, not on behalf of a user.

## Implicit

Asdf

# Scope

Scope is a way to limit an app’s access to a user’s data. Rather than granting complete access to a user’s account, it is often useful to give apps a way to request a more limited scope of what they are allowed to do on behalf of a user.

# OpenID Connect

The OAuth 2.0 framework explicitly does not provide any information about the user that has authorized an application. OAuth 2.0 is a delegation framework, allowing third-party applications to act on behalf of a user, without the application needing to know the identity of the user.

OpenID Connect takes the OAuth 2.0 framework and adds an identity layer on top. It provides information about the user, as well as enables clients to establish login sessions.

# References

- [Open ID](https://openid.net/connect/)
- [OAuth 2.0](https://oauth.net/2/)
- [The OAuth 2.0 Authorization Framework](https://tools.ietf.org/html/rfc6749)
