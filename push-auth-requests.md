# Push Authorization Requests (PAR)
:::
Push Authentication Request is currently in Early Access for [*pricing plan* i.e. Enterprise Private Cloud] customers. You must request access for each tenant from [Auth0 Support](https://support.auth0.com).
:::

[Push Authorization Request (PAR)](https://datatracker.ietf.org/doc/html/rfc9126) is a backend protocol to push authorization requests directly to an authorization server. As part of the [Financial Grade API (FAPI) Security Profile 1.0](https://datatracker.ietf.org/doc/html/rfc9126), PAR adds a layer of security to your authorization requests and protects APIs in high-value scenarios.

## How it works
PAR allows your application to push payloads of OAuth 2.0 authorization requests directly to the authorization server’s PAR endpoint. In response, the authorization server sends a request URI value, `request_uri`, to use when you call the `/authorize` endpoint. The `request_uri` is a reference to the stored authorization requests at the `/par` endpoint so these requests are not exposed.
(media/par.jpg)

## Benefits
One benefit of using push authorization requests is early validation. In other OAuth 2.0 flows, such as Authorization Code Flow, end users are redirected to the authorization server for validation. In PAR, request parameters are validated at the beginning of the authorization request before the end user is redirected.

PAR also passes authorization requests on the back-channel. Front-channel communications rely on an intermediary (e.g. a browser) via appended HTTPS query parameters (GET, POST). Messages are not sent directly. Back-channel communications are passed in the body of an authenticated backend request for a more direct approach.