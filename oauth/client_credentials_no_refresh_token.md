# Client Credentials No Refresh Token

:bulb: When granting Client Credentials via the `grant_type=client_credentials`, the server should not include a refresh token in the response. And therefor clients should not expect the `refresh_token` in the access token response.

> If the access token request is valid and authorized, the
> authorization server issues an access token as described in
> Section 5.1.  A refresh token SHOULD NOT be included.  If the request
> failed client authentication or is invalid, the authorization server
> returns an error response as described in Section 5.2.
>
> -- RFC 6749 "The OAuth 2.0 Authorization Framework" [4.4.3.  Access Token Response](https://www.rfc-editor.org/rfc/rfc6749#section-4.4.3)

:tada: Happy coding!
