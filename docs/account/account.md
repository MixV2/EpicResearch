# Account
To access Epic's services, you will need an account. Each account is assigned a unique 32 character identifier.  
Using your account, you are able to generate an access token which can be used to access areas of Epic's API.

You can access `account-public-service` through any of these domains:
- https://account-public-service-prod.ol.epicgames.com
- https://account-public-service-prod03.ol.epicgames.com
- https://account-public-service-prod.ak.epicgames.com
- https://account-public-service-prod-m.ol.epicgames.com
- https://egp-idsoc-proxy-prod.ol.epicgames.com

## Account Structure
A model of an account looks like:
- `id`: the unique identifier of the account
- `displayName`: the current display name of the account
- `externalAuths`: a list of external auths (e.g. `xbl`, `psn`, `nintendo`)

Keep in mind that there are a lot more attributes, but these are the only ones visible to other users.
