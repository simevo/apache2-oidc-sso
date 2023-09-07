apache2-oidc-sso
================

Proof-of-concept integration of Apache2 with external SSO using Open ID Connect.

This demo is set up to work with Google Open ID, but it should be possible to make it work with [SPID/CIE OpenID Connect](https://docs.italia.it/italia/spid/spid-cie-oidc-docs/it/versione-corrente/index.html).

## Set-up

1. Create the OAuth 2.0 Client IDs in the Google API console: https://console.cloud.google.com/apis/credentials; make sure you add https://localhost:8443 to **Authorized JavaScript origins** and https://localhost:8443/private/redirect_uri to **Authorized redirect URIs**

2. Copy-paste your **Client ID** to `OIDCClientID` and your **Client secret** to `OIDCClientSecret` in the `httpd/httpd-ssl.conf` file

3. Start the local service on your workstation with this command (requires docker and docker-compose):

        docker-compose up

4. Open the webapp at: https://localhost:8443, accept the unsecure SSL cert, and click on the "Go to the private page" link to start the login flow.

## References

- https://hub.docker.com/_/httpd

- https://stackoverflow.com/a/69500324

- https://github.com/OpenIDC/mod_auth_openidc