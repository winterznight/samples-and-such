# Session Management

A session is the interaction between a requestor and a resource while session management is a series of protocols to deter an unauthorized party from hijacking the sessions. Session management becomes more complex when sessions have more than one layer, as in a local layer inside your application, a layer within Auth0, and a layer for any other IdP you may be using. Protocols should be practiced on all existing session layers.

Best practices to secure your sessions include:
<ul>
    <li>
    Set session lifetime limits
    </li>
    <li>
    Session revokation
    </li>
</ul>

## Configure session lifetime limits
Session lifetime is an amount of time the user can maintain interaction with your application without reauthentication. Users can navigate within your application structure without providing credentials for a time limit you can set in the Auth0 session layer. In the Auth0 session layer, you have options for lifetime limits you can configure: an inactivity timeout based on user interaction and a time-based expiration you can specify via the Auth0 Dashboard. To learn more about configuring session lifetime limits, read <a href="https://auth0.com/docs/users/sessions/session-lifetime-limits">Session Lifetime Limits </a>