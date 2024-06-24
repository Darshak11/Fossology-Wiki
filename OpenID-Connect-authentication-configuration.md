# Page is a Work In Progress
# Using OpenID Connect

OpenID Connect is an authentication layer on top of OAuth 2.0 framework. Major authentication providers like Google and Azure already have support for it.

1. [Setting up UI authentication](#setting-up-ui-authentication)
    1. [Prerequisites](#prerequisites)
    2. [Registering application](#registering-application)
    3. [Configure FOSSology](#configure-fossology)
    4. [Test login](#test-login)
    5. [Disabling username-password login](#disabling-username-password-login)
2. [Setting up REST API authentication](#setting-up-rest-api-authentication)
    1. [Benefits of M-2-M token over Bearer tokens](#benefits-of-m-2-m-token-over-bearer-tokens)
    2. [Register with authentication provider](#register-with-authentication-provider)
    3. [Registering client with FOSSology](#registering-client-with-fossology)
    4. [Generating token](#generating-token)
    5. [Verify client id claim](#verify-client-id-claim)
    6. [Test connection](#test-connection)
    7. [Restrict REST API token type](#restrict-rest-api-token-type)

## Setting up UI authentication
For the following process, we are using [Auth0](https://auth0.com) as an authentication provider. However, except for the registration process, everything else should be same for all providers.
### Prerequisites
1. A provider which supports OpenID Connect Authorization Code Flow ([Auth0](https://auth0.com) for example)
2. Network connectivity with provider from the server (server will make some `GET` and `POST` requests to the provider)
3. Administrative account on FOSSology
### Registering application
1. Signup with Auth0 and add a new application as "Regular Web App":
    ![image](https://user-images.githubusercontent.com/18077542/161728305-1a16bcc5-80c0-4095-b1fe-7994358619d9.png)
2. Goto application "Settings" and fill out basic information.
    ![snap](https://user-images.githubusercontent.com/18077542/161729255-f2884202-73e0-4606-9722-5a1281468a77.png)
3. Add "Application Login URI" and "Allowed Callback URLs" to point to your FOSSology homepage.
    ![snap](https://user-images.githubusercontent.com/18077542/161905167-a4ebbfd0-425d-429b-8a0e-bc14a5c4f374.png)
4. Add the server domain to "Allowed Web Origins" and "Allowed Origins (CORS)".
5. Under application setting, goto bottom in Advance Settings and make sure "Authorization Code" Grant Type is checked.
    ![snap](https://user-images.githubusercontent.com/18077542/161731593-90af2023-1607-4705-845f-dd4c4b153ee7.png)
6. Under Applications, goto APIs and copy the "API Audience" URL.
    - Paste this copied URL in your account settings as "Default Audience".
    - Without this step, Auth0 generates a [proprietary access token](https://community.auth0.com/t/why-is-my-access-token-not-a-jwt-opaque-token/31028) and break the application.
    ![snap](https://user-images.githubusercontent.com/18077542/161750550-4e7d8b18-2d3a-49c7-adfd-b42524f10b9e.png)
    ![snap](https://user-images.githubusercontent.com/18077542/161750776-157e4938-b96e-4851-83d3-f476b6fabfc5.png)
### Configure FOSSology
1. Login to FOSSology and head over to "Admin > Customize".
2. Find following fields and fill them.
    - OIDC App Name: The name shown on login button.
    - OIDC Client Id: "Client ID" from Auth0
    - OIDC Secret: "Client Secret" from Auth0
    - Redirect URL: This will be the callback URL (the URL where app is hosted).
      - Make sure the redirect URL matches callback URL in Registering application section.
    - OIDC Discovery URL: Available under "Advanced Settings > Endpoints" as "OpenID Configuration".
    ![snap](https://user-images.githubusercontent.com/18077542/161906217-c14924fe-1402-40a7-a2a9-e39d6701f231.png)
3. Hit "Update" to save the changes. FOSSology will try to pull other URLs from the Discovery URL. Make sure all fields are filled.
    - "Logout URL" is optional and is used to redirect user once they logout.
    ![snap](https://user-images.githubusercontent.com/18077542/161736333-15772779-7bd3-4796-839a-100ed684744a.png)
4. If some of the fields are not populated from discovery url, make sure to fill them manually. All the fields (except Logout URL) are required for OIDC to work.
    - The "OIDC Client Id Claim" is required for REST API authentication and is explained in [Verify client id claim](#verify-client-id-claim) section bellow.
### Test login
1. Create a user in Auth0 under "User Management".
2. Create user with the username as email entered in Auth0.
    - The current authentication mechanism gets the email of user from auth provider and create a session for the user with same username.
3. Logout if you are currently logged in and there should be additional button "Login with (OIDC App Name)" like bellow.
    ![snap](https://user-images.githubusercontent.com/18077542/161737106-df6a5a5a-84e0-4dde-93aa-53c1e8b7a702.png)
4. Try to login with the new button. If there are any errors, they will be mentioned at the message space in UI.
### Disabling username-password login
Once OIDC login is setup on the instance, the password based login can be disabled.
1. Open the `/etc/fossology/fossology.conf` or `/usr/local/etc/fossology/fossology.conf` file.
2. Find the `[AUTHENTICATION]` section and modify `provider` to `external`.
    - Doing so, users will no longer be allowed to use their passwords for login.
3. To revert, simply change the value of `provider` to `password`.

## Setting up REST API authentication
Currently FOSSology uses Bearer tokens for REST API authentication. But with OIDC integration, it can be replaced with OpenID Connect Machine-to-machine tokens.

### Benefits of M-2-M token over Bearer tokens
| Topic | OIDC | FOSSology |
| --- | --- | --- |
| Standard | OAuth 2.0's [Client Credentials Grant](https://oauth.net/2/grant-types/client-credentials/) | Does not follow any standard |
| Life span | Granularity in seconds | Upto 30 days (increment of 1 day) |
| Verification | JWT verification (typically with certificates) | Secure key stored with FOSSology DB |
| Authority | Trusted party | FOSSology server |
| Generating new token | Client id and secret (can be changed anytime) | FOSSology username and password (mostly static) |

With all these benefits and OAuth 2.0 being a standard protocol, accessing FOSSology's REST API will be more easier and secure.

### Register with authentication provider
1. From the auth provider, register a new "Machine to Machine Application". All providers should provide it under "Client Credentials" grant.
    ![snap](https://user-images.githubusercontent.com/18077542/161752436-e1c990aa-fb3d-4147-98fb-d58c56295f04.png)
2. Select your default API and give permission "read:clients" and Authorize. For other providers, this step is optional.
    ![snap](https://user-images.githubusercontent.com/18077542/161752653-8d2fb56c-699a-48ed-9fb7-3196604d82f1.png)
3. Note the "Client ID", "Client Secret" and "OAuth Token URL" (under Settings > Advanced Settings > Endpoints). You will require this to generate tokens for your client.
### Registering client with FOSSology
Since "Client Credentials" does not provide information about the user, FOSSology can not authorize the request. To do so, we can make use of client id to setup the link between user and token as most auth provider inject the client id in the access token.
1. Make sure OIDC tokens are allowed in `fossology.conf`.
    - Open the `/etc/fossology/fossology.conf` or `/usr/local/etc/fossology/fossology.conf` file.
    - Find the `[AUTHENTICATION]` section and modify `resttoken` to `oauth` or `both`.
2. As the intended user, login to FOSSology and navigate to "Admin > Users > Edit User Account".
3. Find "Add new oauth client" and provide the client a name, paste the Client ID from auth provider and select a scope.
    * **Note:** Do copy the client id exactly from MyID Connect portal without any modifications, otherwise verification will always fail.
    * **Note:** One client can have only one scope and can be registered only once. Do fill the scope with care.<br />
    ![snap](https://user-images.githubusercontent.com/18077542/161755809-c622c00e-07cb-464f-90ce-4509d8da6c7e.png)
4. After clicking "Add new client", you should see following message. And clicking on "Reveal" button should display the client id as well.
    ![snap](https://user-images.githubusercontent.com/18077542/161756026-20defcd1-2f5e-4b6f-b737-a77ecce67d26.png)
### Generating token
1. From Quick Start, select an implementation in your language and get the `access_token`.
    - It requires sending a post request to Token endpoint.
    - The request body should contain `"grant_type": "client_credentials"` and respective `client_id` and `client_secret`.<br />
    ![snap](https://user-images.githubusercontent.com/18077542/161753475-e87bb19a-40c2-4b43-a27a-c285ee69b90a.png)
2. Response will contain the `access_token` which can be used while calling FOSSology API.
    ![snap](https://user-images.githubusercontent.com/18077542/161754245-d0992f1e-08f9-4291-bd3e-4546b9b93b11.png)
### Verify client id claim
Different implementations of auth providers exposes client id as different claim. Check the claim used by your provider and modify the default value.
1. Copy the access token provided by the auth provider as described in [Generating token](#generating-token) section.
2. Paste it on a JWT analyzer tool like [jwt.io](https://jwt.io) and look for your client id in payload.
    - As seen in the screenshot bellow, the claim is `azp` and same should be updated.<br />
    ![snap](https://user-images.githubusercontent.com/18077542/161758613-084ca936-5901-4c0a-8f91-233319ebb192.png)
3. Update the "OIDC Client Id Claim" under "Admin > Customize".
    ![snap](https://user-images.githubusercontent.com/18077542/161905990-3b096ad2-09aa-43d9-b09e-8b7a2ea0c65a.png)
### Test connection
1. Use the provided access token as the Bearer token.
2. Request the endpoint `/api/v1/users/self`.
3. If the request was successful and information about your user is returned, the integration was done successfully.
### Restrict REST API token type
The REST API token type can be restricted based on `fossology.conf`.
1. Open the `/etc/fossology/fossology.conf` or `/usr/local/etc/fossology/fossology.conf` file.
2. Find the `[AUTHENTICATION]` section and modify `resttoken`. The value can be:
    - `token`: Allow only old JWT tokens
    - `oauth`: Allow only new OIDC tokens
    - `both`: Allow both old and new tokens

Please open an issue/discussion in case any assistance is required.